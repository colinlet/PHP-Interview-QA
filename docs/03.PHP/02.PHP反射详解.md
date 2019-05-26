# PHP 反射详解

面向对象编程中对象被赋予了自省的能力，而这个自省的过程就是反射。
反射，直观理解就是根据到达地找到出发地和来源。比如，一个光秃秃的对象，我们可以仅仅通过这个对象就能知道它所属的类、拥有哪些方法。
反射是指在PHP运行状态中，扩展分析PHP程序，导出或提出关于类、方法、属性、参数等的详细信息，包括注释。这种动态获取信息以及动态调用对象方法的功能称为反射API。
如何使用反射API

## 如何使用反射 API

```php
class person
{
	public $name;
	public $gender;
	public function say(){
		echo $this->name," \tis ",$this->gender,"\r\n";
	}
	public function set($name, $value)
	{
		echo "Setting $name to $value \r\n";
		$this->$name= $value;
	}
	public function get($name)
	{
		if(!isset($this->$name)){
			echo '未设置';　
			$this->$name="正在为你设置默认值";
		}
  		return $this->$name;
	}
}
$student = new person();
$student->name = 'Tom';
$student->gender = 'male';
$student->age = 24;
```

现在，要获取这个student对象的方法和属性列表该怎么做呢？

```php
// 获取对象属性列表
$reflect = new ReflectionObject($student);
$props　= $reflect->getProperties();
foreach ($props as $prop) {
	print $prop->getName() ."\n";
}
// 获取对象方法列表
$m = $reflect->getMethods();
foreach ($m as $prop) {
	print $prop->getName() ."\n";
}
```

也可以不用反射API，使用class函数，返回对象属性的关联数组以及更多的信息：

```php
// 返回对象属性的关联数组
var_dump(get_object_vars($student));
// 类属性
var_dump(get_class_vars(get_class($student)));
// 返回由类的方法名组成的数组
var_dump(get_class_methods(get_class($student)));
```

假如这个对象是从其他页面传过来的，怎么知道它属于哪个类呢？

```php
// 获取对象属性列表所属的类
echo get_class($student);
```

反射API的功能显然更强大，甚至能还原这个类的原型，包括方法的访问权限等

```php
// 反射获取类的原型
$obj = new ReflectionClass('person');
$className = $obj->getName();
$Methods = $Properties = array();
foreach($obj->getProperties() as $v)
{
	$Properties[$v->getName()] = $v;
}
foreach($obj->getMethods() as $v)　　
{
	$Methods[$v->getName()] = $v;
}
echo "class {$className}\n{\n";
is_array($Properties) && ksort($Properties);
foreach($Properties as $k => $v)
{
	echo "\t";
	echo $v->isPublic() ? ' public' : '',$v->isPrivate() ? ' private' : '',
	$v->isProtected() ? ' protected' : '',
	$v->isStatic() ? ' static' : '';
	echo "\t{$k}\n";
}
echo "\n";
if(is_array($Methods)) ksort($Methods);
foreach($Methods as $k => $v)
{
	echo "\tfunction {$k}(){}\n";
}
echo "}\n";
```

输出如下

```php
class person
{
	public gender
	public name
	function get(){}
	function set(){}
	function say(){}
}
```

不仅如此，PHP手册中关于反射API更是有几十个，可以说，反射完整地描述了一个类或者对象的原型。反射不仅可以用于类和对象，还可以用于函数、扩展模块、异常等

## 反射有什么作用

反射可以用于文档生成。因此可以用它对文件里的类进行扫描，逐个生成描述文档。
既然反射可以探知类的内部结构，那么是不是可以用它做hook实现插件功能呢？或者是做动态代理呢？

```php
class mysql
{
	function connect($db) {
		echo "连接到数据库${db[0]}\r\n";
	}
}
class sqlproxy
{
	private $target;  
	function construct($tar) { 
		$this->target[] = new $tar();
	}
	function call($name, $args) {
		foreach ($this->target as $obj) {
			$r = new ReflectionClass($obj);
			if ($method = $r->getMethod($name)) {
				if ($method->isPublic() && !$method->isAbstract()) {
					echo "方法前拦截记录LOG\r\n";
					$method->invoke($obj, $args);
					echo "方法后拦截\r\n";
				}
			}
		}
	}
}
$obj = new sqlproxy('mysql');
$obj->connect('member');
```

在平常开发中，用到反射的地方不多：一个是对对象进行调试，另一个是获取类的信息。在MVC和插件开发中，使用反射很常见，但是反射的消耗也很大，在可以找到替代方案的情况下，就不要滥用。

PHP有Token函数，可以通过这个机制实现一些反射功能。从简单灵活的角度讲，使用已经提供的反射API是可取的。

很多时候，善用反射能保持代码的优雅和简洁，但反射也会破坏类的封装性，因为反射可以使本不应该暴露的方法或属性被强制暴露了出来，这既是优点也是缺点。