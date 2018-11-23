# Docker
- 添加yum源。
```
# yum install epel-release –y
# yum clean all
# yum list
```
- 安装并运行Docker。
```
# yum install docker-io –y
# systemctl start docker
```
- 检查安装结果。
```
# docker info
```
## 卸载
- 查询安装过的包
```
yum list installed | grep docker
docker-engine.x86_64                 17.03.0.ce-1.el7.centos         @dockerrepo
```
- 删除安装的软件包

`yum -y remove docker-engine.x86_64`

