# OpenCV下载（源码编译）

- 下载对应版本的本体源码和拓展源码（应该是opencv 和 opencv_contrib）

- 下载依赖

  ```
  sudo apt update
  sudo apt install mlocate
  sudo updatedb
  sudo apt install build-essential cmake git libgtk-3-dev pkg-config
  sudo apt install libavcodec-dev libavformat-dev libswscale-dev 
  sudo apt install libv4l-dev libxvidcore-dev libx264-dev openexr
  sudo apt install libatlas-base-dev libopenexr-dev
  sudo apt install libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev
  sudo apt install python3-dev python3-numpy libtbb2 libtbb-dev libjpeg-dev
  sudo apt install libpng-dev libtiff-dev libdc1394-dev gfortran
  sudo apt install libavutil-dev libopenblas-dev
  sudo apt install libhdf5-dev liblapack-dev libblas-dev libavformat-dev
  ```

  备用版本：

  ```
  sudo apt-get update
  sudo apt-get upgrade
  sudo apt-get install build-essential
  sudo apt-get install g++
  sudo apt-get install cmake git pkg-config 
  sudo apt-get install libjpeg8-dev 
  sudo apt-get install libtiff5-dev 
  sudo apt-get install libopenjp2-7-dev
  sudo apt-get install libpng-dev
  sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
  sudo apt-get install libgtk2.0-dev
  sudo apt-get install libatlas-base-dev gfortran
  ```

  若提示版本不匹配，还是去搜一下替代版本吧（直接去问AI算了）

- 解压压缩包，并在目录下创建build文件夹，进入

  - cmake一下

    ```
    cmake -D CMAKE_BUILD_TYPE=Release \
          -D CMAKE_INSTALL_PREFIX=/opt/opencv \
          -D INSTALL_C_EXAMPLES=ON \
          -D INSTALL_PYTHON_EXAMPLES=ON \
          -D OPENCV_GENERATE_PKGCONFIG=ON \
          -D BUILD_EXAMPLES=ON \
          -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
          -D WITH_GTK=ON \
          -D BUILD_opencv_world=OFF \
          -D BUILD_opencv_java=OFF \
          ..
    ```

    终端cmake之后产生的文件内容不能有红色报错，有橙色警告可以忽视

  - make一下

    ```
    make
    ```

  - ```
    sudo make install
    ```

  - ```
    sudo gedit /etc/ld.so.conf.d/opencv.conf 
    ```

    打开后可能是空文件，在文件内容最后添加：

    ```
    /usr/local/lib
    ```

  - 然后保存文件 输入指令刷新使规则生效：

    ```
    sudo ldconfig
    ```

  - ```
    sudo vim /etc/bash.bashrc
    ```

    末尾输入：

    ```
    PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/opt/opencv/lib/pkgconfig
    export PKG_CONFIG_PATH
    ```

    输入指令刷新使规则生效：

    ```
    source /etc/bash.bashrc
    ```

  - ```
    vim ~/.bashrc
    ```

    末尾输入：

    ```
    export CMAKE_PREFIX_PATH=/opt/opencv:$CMAKE_PREFIX_PATH
    ```

    输入指令刷新使规则生效：

    ```
    source ~/.bashrc
    ```

  ***

  安装至此结束，快去测试一下你的opencv吧！

