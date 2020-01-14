# PHP 数组

## 简介

这些函数允许你通过不同的方式来使用和操作数组。数组是存储、管理和操作变量组的必不可少的工具。

PHP 支持简单数组和多维数组，数组可由用户自己创建也可以由其它函数创建。有很多特殊的数据库处理函数可以从数据库查询中返回数组以及一些返回数组的函数。

## 预定义常量

下列常量作为 PHP 核心的一部分总是可用的。

CASE_LOWER (integer)

> CASE_LOWER 用在 array_change_key_case() 中将数组的键名转换成小写字母。这也是 array_change_key_case() 的默认值。

CASE_UPPER (integer)

> CASE_UPPER 用在 array_change_key_case() 中将数组的键名转换成大写字母。
排序顺序标识：

SORT_ASC (integer)

> SORT_ASC 用在 array_multisort() 函数中，使其升序排列。

SORT_DESC (integer)

> SORT_DESC 用在 array_multisort() 函数中，使其降序排列。

- 排序类型标识：用于各种排序函数

SORT_REGULAR (integer)

> SORT_REGULAR 用于对对象进行通常比较。

SORT_NUMERIC (integer)

> SORT_NUMERIC 用于对对象进行数值比较。

SORT_STRING (integer)

> SORT_STRING 用于对对象进行字符串比较。

SORT_LOCALE_STRING (integer)

> SORT_LOCALE_STRING 基于当前区域来对对象进行字符串比较。PHP 4.4.0 和 5.0.2 新加。

COUNT_NORMAL (integer)

COUNT_RECURSIVE (integer)

EXTR_OVERWRITE (integer)

EXTR_SKIP (integer)

EXTR_PREFIX_SAME (integer)

EXTR_PREFIX_ALL (integer)

EXTR_PREFIX_INVALID (integer)

EXTR_PREFIX_IF_EXISTS (integer)

EXTR_IF_EXISTS (integer)

EXTR_REFS (integer)

## 对数组进行排序

PHP 有一些用来排序数组的函数

主要区别有：

- 有些函数基于 array 的键来排序， 而其他的基于值来排序的：$array['key'] = 'value';。
- 排序之后键和值之间的关联关系是否能够保持， 是指排序之后数组的键可能 会被重置为数字型的（0,1,2 ...）。
- 排序的顺序有：字母表顺序， 由低到高（升序）， 由高到低（降序），数字排序，自然排序，随机顺序或者用户自定义排序。
- 注意：下列的所有排序函数都是直接作用于数组本身， 而不是返回一个新的有序的数组。
- 以下函数对于数组中相等的元素，它们在排序后的顺序是未定义的。 （也即相等元素之间的顺序是不稳定的）。

|函数名称|排序依据|数组索引健保持|排序的顺序|相关函数|
|-|-|-|-|-|
|array_multisort()|值|键值关联的保持，数字类型的不保持|第一个数组或者由选项指定|array_walk()|
|asort()|值|是|由低到高|arsort()|
|arsort()|值|是|由高到低|asort()|
|krsort()|键|是|由高到低|ksort()|
|ksort()|键|是|由低到高|asort()|
|natcasesort()|值|是|自然排序，大小写不敏感|natsort()|
|natsort()|值|是|自然排序|natcasesort()|
|rsort()|值|否|由高到低|sort()|
|shuffle()|值|否|随机|array_rand()|
|sort()|值|否|由低到高|rsort()|
|uasort()|值|是|由用户定义|uksort()|
|uksort()|键|是|由用户定义|uasort()|
|usort()|值|否|由用户定义|uasort()|

## 数组函数

array_change_key_case — 将数组中的所有键名修改为全大写或小写

array_chunk — 将一个数组分割成多个

array_column — 返回数组中指定的一列

array_combine — 创建一个数组，用一个数组的值作为其键名，另一个数组的值作为其值

array_count_values — 统计数组中所有的值

array_diff_assoc — 带索引检查计算数组的差集

array_diff_key — 使用键名比较计算数组的差集

array_diff_uassoc — 用用户提供的回调函数做索引检查来计算数组的差集

array_diff_ukey — 用回调函数对键名比较计算数组的差集

array_diff — 计算数组的差集

array_fill_keys — 使用指定的键和值填充数组

array_fill — 用给定的值填充数组

array_filter — 用回调函数过滤数组中的单元

array_flip — 交换数组中的键和值

array_intersect_assoc — 带索引检查计算数组的交集

array_intersect_key — 使用键名比较计算数组的交集

array_intersect_uassoc — 带索引检查计算数组的交集，用回调函数比较索引

array_intersect_ukey — 用回调函数比较键名来计算数组的交集

array_intersect — 计算数组的交集

array_key_exists — 检查数组里是否有指定的键名或索引

array_key_first — Gets the first key of an array

array_key_last — Gets the last key of an array

array_keys — 返回数组中部分的或所有的键名

array_map — 为数组的每个元素应用回调函数

array_merge_recursive — 递归地合并一个或多个数组

array_merge — 合并一个或多个数组

array_multisort — 对多个数组或多维数组进行排序

array_pad — 以指定长度将一个值填充进数组

array_pop — 弹出数组最后一个单元（出栈）

array_product — 计算数组中所有值的乘积

array_push — 将一个或多个单元压入数组的末尾（入栈）

array_rand — 从数组中随机取出一个或多个单元

array_reduce — 用回调函数迭代地将数组简化为单一的值

array_replace_recursive — 使用传递的数组递归替换第一个数组的元素

array_replace — 使用传递的数组替换第一个数组的元素

array_reverse — 返回单元顺序相反的数组

array_search — 在数组中搜索给定的值，如果成功则返回首个相应的键名

array_shift — 将数组开头的单元移出数组

array_slice — 从数组中取出一段

array_splice — 去掉数组中的某一部分并用其它值取代

array_sum — 对数组中所有值求和

array_udiff_assoc — 带索引检查计算数组的差集，用回调函数比较数据

array_udiff_uassoc — 带索引检查计算数组的差集，用回调函数比较数据和索引

array_udiff — 用回调函数比较数据来计算数组的差集

array_uintersect_assoc — 带索引检查计算数组的交集，用回调函数比较数据

array_uintersect_uassoc — 带索引检查计算数组的交集，用单独的回调函数比较数据和索引

array_uintersect — 计算数组的交集，用回调函数比较数据

array_unique — 移除数组中重复的值

array_unshift — 在数组开头插入一个或多个单元

array_values — 返回数组中所有的值

array_walk_recursive — 对数组中的每个成员递归地应用用户函数

array_walk — 使用用户自定义函数对数组中的每个元素做回调处理

array — 新建一个数组

arsort — 对数组进行逆向排序并保持索引关系

asort — 对数组进行排序并保持索引关系

compact — 建立一个数组，包括变量名和它们的值

count — 计算数组中的单元数目，或对象中的属性个数

current — 返回数组中的当前单元

each — 返回数组中当前的键／值对并将数组指针向前移动一步

end — 将数组的内部指针指向最后一个单元

extract — 从数组中将变量导入到当前的符号表

in_array — 检查数组中是否存在某个值

key_exists — 别名 array_key_exists

key — 从关联数组中取得键名

krsort — 对数组按照键名逆向排序

ksort — 对数组按照键名排序

list — 把数组中的值赋给一组变量

natcasesort — 用“自然排序”算法对数组进行不区分大小写字母的排序

natsort — 用“自然排序”算法对数组排序

next — 将数组中的内部指针向前移动一位

pos — current 的别名

prev — 将数组的内部指针倒回一位

range — 根据范围创建数组，包含指定的元素

reset — 将数组的内部指针指向第一个单元

rsort — 对数组逆向排序

shuffle — 打乱数组

sizeof — count 的别名

sort — 对数组排序

uasort — 使用用户自定义的比较函数对数组中的值进行排序并保持索引关联

uksort — 使用用户自定义的比较函数对数组中的键名进行排序

usort — 使用用户自定义的比较函数对数组中的值进行排序
