


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



