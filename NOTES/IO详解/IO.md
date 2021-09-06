## IO流

IO是指对数据流的输入和输出，也称为IO流，主要分为**字节流**和**字符流**。

字节流可以处理任何类型的数据，如图片、视频等

字符流只能处理字符类型的数据

![img](D:\597\JAVA\src\IO)

### File类

File类是对文件系统中文件以及文件夹进行操作的类

文件创建操作如下，主要涉及**文件创建、删除文件、获取文件描述符**等

```java
class FileDemo{
	public static void main(String[] args){
        File file = new File("D:\\file.txt");
        try{
			f.createNewFile();	//创建一个文件	
            
            // File类的两个变量
			//路径分隔符(与系统有关的）<windows里面是 ; linux里面是 ： >
			System.out.println(File.pathSeparator); // ;
			//路径分隔符(与系统有关的）<windows里面是 \ linux里面是 / >
			System.out.println(File.separator); // \
			// 删除文件
                /*
                File file = new File(fileName);
                if(f.exists()){
                f.delete();
                }else{
                System.out.println("文件不存在");
                }
                */
			}catch (Exception e) {
				e.printStackTrace();
        }
    }
}
```

创建文件

```java
File(String directoryPath);
File(String directoryPath, String filename);
File(File dirObj, String filename);
//directoryPath是文件的路径名，filename是文件名，dirObj是一个 File 对象
```

```java
File file = new File("D:\\java\\file1.txt"); //双\\是转义
System.out.println(file);
File file2 = new File("D:\\java","file2.txt");//父路径，子路径--可使用于多个文件的
System.out.println(file2);
File parent = new File("D:\\java");
File file3 = new File(parent,"file3.txt");//File类的父路径、子路径
System.out.println(file3);
```

**File类方法**

| 方法                              | 描述                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| public String getName()           | 返回此路径名表示的文件或目录的名称                           |
| public String getParent()         | 返回此路径名的父路径名的字符串                               |
| public String getPath()           | 将此路径名转换为一个路径名字符串                             |
| public boolean isFile()           | 测试此路径名标识的文件是否是一个标准文件                     |
| public boolean equals(Object obj) | 测试此路径名与给定对象是否相等                               |
| public String[] list()            | 返回此路径名所表示的目录中文件和目录的名称所组成的字符串数组 |
| public boolean mkdir()            | 创建此路径名指定的目录                                       |
| public String getAbsoultePath()   | 返回路径名的绝对路径名字符创                                 |
| public boolean exists()           | 测试此路径标识的文件或目录是否存在                           |

### 基础IO类和相关方法

最基本的四个抽象类：**ImputStream、OutputStream、Reader、Writer**

最基本的方法：read()、write()

其他流都是上面四种流的子类

#### InputStream

定义了java**流式字节输入模式**的抽象类，该类所有方法在出错条件下抛出IOException异常，主要方法如下

![image-20210906103620505](D:\597\JAVA\src\InputStream.png)

#### OutputStream

定义了java**流式字节输出模式**的抽象类，该类所有方法返回一个void值，并且在出错条件下抛出IOException异常，主要方法如下

![image-20210906103909865](D:\597\JAVA\src\OutputStream.png)

#### Reader

定义了java**流式字符输入模式**的抽象类，该类所有方法在出错条件下抛出IOException异常，主要方法如下

![image-20210906111016649](D:\597\JAVA\src\Reader.png)

**Writer类**

定义了java**流式字符输出模式**的抽象类，该类所有方法返回一个void值，并且在出错条件下抛出IOException异常，主要方法如下

![image-20210906111104304](D:\597\JAVA\src\Writer.png)