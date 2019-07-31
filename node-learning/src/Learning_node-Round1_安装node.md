> [参考教程](https://github.com/nswbmw/N-blog/blob/master/book/1.1%20Node.js%20%E7%9A%84%E5%AE%89%E8%A3%85%E4%B8%8E%E4%BD%BF%E7%94%A8.md)
> 方法一：下载官方安装包，下载之后，进行解压使用
> 方法二：下载源码 ，进行编译安装
> 方法三：Linux用户可以使用yum 或者 apt-get进行安装
> 方法四：Mac可以使用homebrew安装

### Windows、Mac用户
- 前往官网，选择左侧LST长期支持版本，或者想尝鲜可以选择最新版本，支持新特性；
- 双击运行下载的安装包，就开始安装流程，会选择默认安装路径；
- 最后就安装完毕，就可以通过指令node -v/npm -v查看版本了，npm也会安装完毕

### Linux 用户
- 选择好版本，然后使用命令，下载源码之后编译
```text
curl -O https://nodejs.org/dist/v6.9.1/node-v6.9.1.tar.gz
tar -xzvf node-v6.9.1.tar.gz
cd node-v6.9.1
./configure
make
make install
```


[node学习笔记](https://github.com/chyingp/nodejs-learning-guide)