3.字符串(str)
^^^^^^^^^^^^^^^^

a.字符串定义
-------------------
由''或""表示的一系列元素组成的无序序列

**与C++不同，Python中单引号，双引号均可用于字符串**

----

b.字符串中的特殊操作
-----------------------
①join方法
 | 例：','.join(['a', 'b', 'c'])，返回'a, b, c'
	表示将列表中的字符串元素抽出，插入原字符串后合成一个新的字符串
	
②orf函数，chr函数
 | orf()接受长度为一的字符串参数，返回其在Unicode中编号
    
   chr()接受整数参数，返回Unicode中对应字符
 
③转义字符
 | 表示为\+小写字符
   
   需要转义字符不被解析的方法
	使用\\或者在字符串引号之前加上r

----

c.序列的拆包操作
--------------------
①
::
	mystring = 'hello'
	a1, a2, a3, a4, a5 = mystring
	则5个元素分别赋给5个变量

②
::
     a = [1, 2, 3]
	 
     ``b = [*a, 4]``    `其中*表示拆包操作`
	 
     则b = [1, 2, 3, 4]

序列均支持拆包操作