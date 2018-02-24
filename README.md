# ZK_ImageServer
an effective ImageServer(implement by reactor)
##高性能图像处理服务器##
　　　功能：支持高并发的图像处理功能，如：图像的远端存储，图像的中值滤波，模糊，去噪，以及超分辨率恢复，远端存储等。
　　　技术思路如下：
　　　１.图像处理器的网络部分采用的是reactors in threads的思路编写的，支持高并发（并发量尚未进行测试，但至少会大于等于单机epoll服务器支持的并发量）。
　　　２.数据库部分采用的是Mysql（数据库部分相对简单一些），只负责记录用户的登录信息（如登录账户密码，上次登录时间），以及为用户开辟的独立存储文件夹位置等．
　　　３.图像处理算法部分采用c++的opencv的库函数进行编写，超分辨率恢复模块拟采用GAN的方式编写。
  
关于整个代码的框架以及技术细节，可参考代码注释和我的技术博客（http://blog.csdn.net/zk3326312/article/category/7438372，高性能图像处理服务器系列文章）。
  
