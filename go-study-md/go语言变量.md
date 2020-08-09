#go语言变量
变量来源于数学，是计算机语言中能储存计算结果或能表示值抽象概念。  
变量可以通过变量名访问。  
Go 语言变量名由字母、数字、下划线组成，其中首个字符不能为数字。  
声明变量的一般形式是使用 var 关键字：

    var identifier type
可以一次声明多个变量：

    var identifier1, identifier2 type
##变量声明
####第一种，指定变量类型，如果没有初始化，则变量默认为零值。
	var v_name v_type
	v_name = value
零值就是变量没有做初始化时系统默认设置的值。
+ 数值类型（包括complex64/128）为 0

+ 布尔类型为 false

+ 字符串为 ""（空字符串）

+ 以下几种类型为 nil：


		var a *int
		var a []int
	    var a map[string] int
	    var a chan int
	    var a func(string) int
	    var a error // error 是接口
####第二种，根据值自行判定变量类型。

    var v_name = value
####第三种，省略 var, 注意 := 左侧如果没有声明新的变量，就产生编译错误，格式：


    v_name := value

	var intVal int 
	intVal :=1 // 这时候会产生编译错误
	intVal,intVal1 := 1,2 // 此时不会产生编译错误，因为有声明新的变量，因为 := 是一个声明语句

	可以将 var f string = "Runoob" 简写为 f := "Runoob"：
###多变量声明

    //类型相同多个变量, 非全局变量
    var vname1, vname2, vname3 type
    vname1, vname2, vname3 = v1, v2, v3
    
    var vname1, vname2, vname3 = v1, v2, v3 // 和 python 很像,不需要显示声明类型，自动推断
    
    vname1, vname2, vname3 := v1, v2, v3 // 出现在 := 左侧的变量不应该是已经被声明过的，否则会导致编译错误
    
    // 这种因式分解关键字的写法一般用于声明全局变量
    var (
    	vname1 v_type1
    	vname2 v_type2
    )
####值类型和引用类型
所有像 int、float、bool 和 string 这些基本类型都属于值类型，使用这些类型的变量直接指向存在内存中的值