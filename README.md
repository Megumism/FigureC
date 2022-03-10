# 说明

## 功能

`bmp_read.c`实现了对未压缩的`.bmp`文件的头信息进行terminal输出，对其中二进制编码的像素进行文本编码的输出，输出文件中的编码顺序为左上至右下。

## 参考

本代码参考了

- [【原创】C语言读取BMP格式图片](https://www.cnblogs.com/gengzj/p/3827077.html)
- [BMP文件解析](https://www.cnblogs.com/velscode/p/10475040.html#c%E8%AF%AD%E8%A8%80%E4%BB%A3%E7%A0%81)

两篇文章，其中代码框架基于前文，并在后文的知识基础上进行了修订：

- 将`fopen`参数改为由`'r+'`改为`'rb+'`避免`fread`因读到结束符字节而停止。
- 将`BitCount`修改为读入两个字节而不是四个，修正了错误。
- 将读入DataPart的代码修正为随BitCount扩大而扩大，避免成倍数的漏读。