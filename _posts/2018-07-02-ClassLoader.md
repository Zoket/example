- 一般来说，Java源文件（.java文件）经过编译变成字节码文件（.class文件），类加载器读取字节码，转换成java.lang.Class的一个实例。

- 基本上所有的类加载器都是java.lang.ClassLoader类的一个实例。

+ 类加载器的分类：
   1. 引导类加载器（bootstrap class loader）加载Java核心库，不继承自java.lang.Classloder。
   2. 扩展类加载器（extensions class loader）加载java扩展库。
   3. 系统类加载器（system class loader）根据CLASSPATH来加载Java类，一般来说，Java应用的类都是由它来加载完成的。可以通过ClassLoader.getSystemClassLoader
()来获取。

以上三个分类是依照从上到下的顺序依次继承的。

- 类加载器在尝试查找某个类的字节代码并定义它的时候，会先代理给其父类加载器，由父类加载器先去尝试加载这个类，以此类推。

- 