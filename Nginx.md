# Nginx

- 安装make

  `yum -y install gcc automake autoconf libtool make`

- 安装C++

  `yum install gcc gcc-c++`

- 安装**PCRE**库

  - 进入自定义目录

    `cd /home/src`

  - 下载最新的库

    地址：<u>ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/</u>

    在该地址中选最新的pcre-XXXX.tar.gz包

    ```
    wget ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre-8.38.tar.gz 
    tar -zxvf pcre-8.38.tar.gz
    cd pcre-8.38
    ./configure
    make
    make install
    ```

- 安装**zlib**库

  ```
  wget http://zlib.net/zlib-1.2.11.tar.gz
  tar -zxvf zlib-1.2.11.tar.gz
  cd zlib-1.2.11
  ./configure
  make
  make install
  ```

- 安装**ssl**

  ```
  wget https://www.openssl.org/source/openssl-1.0.1t.tar.gz
  tar -zxvf openssl-1.0.1t.tar.gz
  cd openssl-1.0.1t.tar
  ./config
  make
  make install
  ```

- 安装Nginx

  ```
  wget http://nginx.org/download/nginx-1.4.2.tar.gz
  tar -zxvf nginx-1.4.2.tar.gz
  cd nginx-1.4.2
  
  ./configure --sbin-path=/usr/local/nginx/nginx \
  --conf-path=/usr/local/nginx/nginx.conf \
  --pid-path=/usr/local/nginx/nginx.pid \
  --with-http_ssl_module \
  --with-pcre=/home/src/pcre-8.38 \
  --with-zlib=/home/src/zlib-1.2.11 \
  --with-openssl=/home/src/openssl-1.0.1t
  
  make
  make install
  ```

  *--with-pcre、--with-zlib、--with-openssl都是前面安装的源码路径*

- 运行

  `/usr/local/nginx/nginx`
