# Lucene全文检索技术

> Lucene是一个基于java开发全文检索工具包。

### 全文检索应用场景
 + 1.搜索引擎
	+ 百度，360，搜狗，搜狐
 + 2.站内网站
 	+ 论坛搜索，微博，文章搜索
 + 3.电商搜索
 	+ 淘宝搜索，京东搜索


**只要有搜索的地方都可以使用全文检索技术**

```tex
Document 
1. 文件名称 （域）
2. 文件路径 （域）
3. 文件内容 （域）
4. 文件大小 （域）
		.
		.
		.

```

### 索引和搜索实现流程
 + 1.创建索引
 	+ 获取文档
 		+ 原始文档：基于哪些数据进行搜索，那么这些数据就是原始文档。
	 	 	+ 搜索引擎：使用爬虫获取原始文档。
		 	 	+ 站内搜索：数据库中的数据
			 	 	+ 案例：直接使用io流，获取文档。
 + 2.构建文档对象
 	+ 对应每个原始文档创建一个Document对象
 	+ 每个Document对象中包含多个域(Field --字段),域中保存着原始数据
 	+ 域的名称
 	+ 域的值
 	+ 每个文档都有一个唯一的编号
 + 3.分词
   +  分析文档就是分词的过程
   +  先根据空格进行字符串的拆分，得到一个单词列表
   +  全部转换成小写，忽略大小写不敏感
   +  去掉标点符号
   +  去除停用词 （and,a等等） 无意义的词
   +  每个关键词都封装成一个term对象
   +  term中包含两部分内容，关键词所在的域,关键词本身
   +  不同的域中拆分出来相同的关键字是不同的term
 + 4.创建索引
 	+ 基于关键词列表来创建一个索引，保存到磁盘中（索引库中）一次创建多次使用
 	+ 索引库中包含：1，索引 2，Document 3，关键词和文档的对应关系  一个关键词对应着一个链表（链表中保存着文档id） 倒排索引结构 通过关键词，词语来找文档 

  

### 查询索引

   + 1.用户查询接口
      	   + 用户输入查询条件的地方
      		+ 例如：百度的搜索框 
  + 2.把关键字封装成一个查询对象
	 	   +  要查询的域
     +  要查询的关键词

  + 3.执行查询
    + 找到关键词，根据关键词来找到对应的文档
    + 根据要查询的关键词找到对应的域上进行搜索
    + 渲染结果


 ### 入门程序

   + 环境 ： 下载 	Lucene

   	  



 