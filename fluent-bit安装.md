fluent-bit安装



参考 https://docs.fluentbit.io/manual/installation/build_install

    git clone https://github.com/fluent/fluent-bit
    tar xzf fluent.bit.xx.tgz
    cd build
    cmake3 ../
    make
    make install


    vim /usr/lib/systemd/system/fluent-bit.service
    修改一下配置文件为绝对路径
    /usr/local/bin/fluent-bit -c /usr/local/etc/fluent-bit/fluent-bit.conf
    
    systemctl start fluent-bit
    systemctl enable fluent-bit