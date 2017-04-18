


## Names

### Package names

简短、简洁、易理解

小写单词

在代码中不需要唯一

不需要考虑包名冲突，冲突时可以起别名

使用包名引用导出名称避免结巴：

bufio.Reader 而不是 bufio.BufReader

如果包仅有一个导出的类型，该类型的构造函数直接用 New 即可，例如 ring.New

简短名称加文档注释，比起长名称更有用

### Getters

获取器（getter）直接使用字段名的导出形式（首字母大写）

设置器（setter）使用 Set 前缀

### Interface names

一个方法的接口，名称为方法名加 -er 后缀


## Control structures

### Redeclaration and reassignment

	f, err := os.Open(name)
	d, err := f.Stat()

函数的形参、返回值变量与函数体具有相同的作用域

### Type switch

查明接口变量的动态类型，与类型断言句法相同，括号中使用关键字 type

习惯用法会在 switch 表达式重用变量名 t，实际上重新声明了一个名字相同但类型不同的变量

	var t interface{}
	t = functionOfSomeType()
	switch t := t.(type) {
	default:
		fmt.Printf("unexpected type %T", t)       // %T prints whatever type t has
	case bool:
		fmt.Printf("boolean %t\n", t)             // t has type bool
	case int:
		fmt.Printf("integer %d\n", t)             // t has type int
	}

## Functions

### Defer
defer 一般用户释放锁或关闭文件

defer 关闭文件，具有 2 个优点：

* 确保在函数返回时能够关闭文件，不用管修改代码时增加返回路径遗忘关闭
* 关闭操作靠近打开操作 -- 比起放在函数的末尾 -- 看起来会更加清晰

defer 语句执行的时候，函数的实参就会被计算


