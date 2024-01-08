# main

- 自己学习过程中造的一些轮子，也算是小型的工具库或者框架吧

- 很久之前看到了`boost`开源库，就想着自己写轮子，虽然不是很完善，但是也是自己学习过程中的一些记录

- `main`分支

  - 这个分支是发布分支，具有`sudo make install`的功能安装到本地

- `install.sh`
  - 安装脚本，全自动化的进行编译构建并且将头文件和静态库安装到本地
  - 如果想手动构建，按照脚本中的内容逐步操作即可

- `uninstall.sh`
  - 卸载脚本，用于将本地头文件和静态库的内容删除

- 关于头文件和静态库

  - 发布的文件是以头文件和对应的静态库实现的

    - 头文件放在`/usr/include/lzx0626`下
    - 静态库放在`/lib64`下

  - 如何使用？

    - 头文件的位置保证了能被系统自动识别

    - 静态库的位置保证了能被系统自动识别位置

    - 但是`g++`和`gcc`的默认链接库没有我们的自定义库，所以即使能够找到位置，也就是不用`-L`参数，还是要通过`-l`参数来指定该库

      - 例如代码中

        ```cpp
        #include <lzx0626/math/...>
        ```

        表明了使用的库是`math`，因此编译时加上`-l llzx0626math`的参数，为了标识唯一性，加上了前缀`lzx0626`


