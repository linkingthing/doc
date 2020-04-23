

打包好的iso镜像文件在
10.0.0.31:/tmp/ddi.iso
ssh密码 123456



## 制作iso参考 

基本上都参考这个 https://www.jianshu.com/p/85f333eda212

### 复制系统光盘已有的文件

mount /dev/cdrom /media/

yum install -y createrepo mkisofs isomd5sum squashfs-tools

mkdir /ISO
/usr/bin/rsync -a --exclude=Packages/ --exclude=repodata/ /mnt/cdrom/ /ISO/ 

chmod +w /ISO/isolinux/isolinux.cfg




#### 安装本地的rpm

安装一些要在新的系统中需要的包 resolve自动解析所有依赖的包

 yumdownloader --resolve xxxx(包名)

安装完毕后，把所有的rpm文件复制到新的Packages目录下

rpm -qa > /root/install.log

awk '{print $0}' /root/install.log | xargs -i cp /media/Packages/{}.rpm /ISO/Packages



#### 生成ks配置，默认安装这些rpm

​	cp /root/anaconda-ks.cfg /ISO/isolinux/ks.cfg

​	在%packages与%end中间加入需要自定义安装的包组

​	cat /root/install.log >> ks.cfg  编辑文件把rpm名放在%packages与%end中间

#### 重新生成comps文件

​	cp /media/repodata/*-x86_64-comps.xml /ISO/repodata/comps.xml

​	createrepo -g repodata/comps.xml ./



### 生成iso文件

    mkisofs -o /tmp/boot2.iso -b isolinux.bin -c boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -V "CentOS7" -R -J -v -T isolinux/. .  
    implantisomd5 /tmp/boot2.iso
    scp /tmp/boot2.iso root@10.0.0.79:/mnt/develop/

  

