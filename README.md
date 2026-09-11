# xcat_on_kylin

**xCAT(Extreme Cloud Administration Toolkit)** 是一个开源的集群管理软件，但xcat-dep包中，并不包含针对KylinV10SP3的支持，重新编译xcat-dep的源码，让 xCAT 支持 Kylin OS

当前，只支持 xcat 2.17.0 版本。

**安装：**

先解压 xcat-core-2.17.0-linux.tar.bz2，并添加安装源

```
tar xjvf xcat-core-2.17.0-linux.tar.bz2
cd xcat-core
./mklocalrepo.sh
```

不需要xcat-dep-2.17.0-linux.tar.bz2，直接下载 xcat-dep-2.17.0-kylin10.3-all.tar.gz，然后解压，并添加安装源

```
tar xzvf xcat-dep-2.17.0-kylin10.3-all.tar.gz
cd xcat-dep-kylin10.3
./mklocalrepo.sh
```

然后安装xCAT

```
yum install xCAT
```

为了让xcat可以识别Kylin V10 SP3的光盘，并且支持KylinV10 SP3相关的模板，下载 xcat-2.17.0-kylinv10sp3-patch.tar.gz，并解压到/opt/xcat目录下

```
tar xzvf xcat-2.17.0-kylinv10sp3-patch.tar.gz -C /opt/xcat
```

对于KylinV10 SP3，xCAT系统内的标识定义为kylin10.3

```
copycds Kylin-Server-V10-SP3-2403-Release-20240426-X86_64.iso
Copying media to /install/kylin10.3/x86_64
Media copy operation successful
```

```
lsdef -t osimage
kylin10.3-x86_64-install-compute  (osimage)
```

