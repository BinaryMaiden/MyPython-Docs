5.字典(dict)
^^^^^^^^^^^^^^^^^^^

a.字典的定义
------------------
一种有索引的数据，每个变量value对应一个索引key,其中key必须是不可变的数据，且在字典中不能重复

----

b.主要方法
--------------
①keys，values，items
::
分别返回所有键(索引)，所有变量，所有键值对(元组形式)
`注：这三者返回的都是list类型数据`
**遍历一个字典只需遍历其key，即可用dict[key]来访问对应的value，故key的重要性更高**

②clear
::
字典清空，删除所有键对值
 
③get
::
(用于保证取到值)
操作格式：
dict.get(key, default=None)
若key存在，则返回对应value，否则返回对应的default参数(默认为None)

③pop
::
效果同之前其他序列的pop方法，接受参数key，弹出其对应的value
 
④字典更新(update方法)
::
dict1.update(dict2)
将dict2中的键值对加入dict1中
**当dict1和dict2中存在相同键时，dict2的值将覆盖dict1的值(新的覆盖旧的)**
	
----

c.字典合并的方法
---------------------------
①两次update
 | 用一个空字典分别更新字典x和字典y，得到了x与y的合并(更新x和y的顺序将影响结果)

②先copy再update
 | 先copy其中一个再update另一个(顺序有影响)
 
③先构造再update
 | dict1 = dict(dict0),得到了一个副本此时dict1，再update(原理同上)
 
④使用dict函数关键字hack
::
``dict3 = dict(dict1, **dict2)``
本质为利用了函数传参的技巧，故仅适用于dict2所有的key均为字符串的情形(数字不能作为形参名称)
	
⑤字典推导式
::
d = {k:v for t in[d1, d2] for k,v in t.items}
`比较复杂，本质上为循环的嵌套`

⑥列表元素的拼接
::
d = dict(list(d1.items()) + list(d2.items()))
**注:必须要有具有k,v结构的特殊列表才能转化为字典，如上述生成的两个列表中的元素均为(a, b)型的元组**
	
⑧导入模块函数chain和ChainMap
::
from collections import ChainMap
d3 = ChainMap(d1,d2),此时生成一个chainmap对象
再将d3转换为dict型数据

⑨利用字典拆包**(最佳方法)**
 | ``dict3 = {**dict1, **dict2}``
 
----
 
d.利用字典实现多分支功能(重要应用)
--------------------------------------------
::	
用于实现类似于C++中switch的作用
先将所有分支放在字典中，根据输入的键提取相应的值，实现多分支




























