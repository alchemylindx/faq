服务器部署与运维
====

> [管理平台配置说明](spec/server_config.md)

我们提供了两种方式搭建自己的服务器，基于基于jar包或者Docker部署服务器。

**重要 jar包，docker镜像两者任选其一。**

* [基于jar包部署服务器](#jar)
* [访问站点服务器](#loginSite)
* [基于Docker部署服务器](#docker)

## **部署服务器**

### <h3 id="jar">**基于jar包部署服务器**<h3>

* 项目地址: 
* 最新版本:
	* [Github下载](<https://github.com/akaxincom/openzaly/releases>)
	* Gitee下载: 完善中

* 启动命令：

```
java -jar openzaly-server.jar
```
* 支持的启动参数：
```
java -jar openzaly-server.jar -h
```
```
  -Dsite.project.env    openzaly server environment default:ONLINE
  -Dsite.version        openzaly server version default:0.3.2
  -Dsite.address        openzaly Netty address default:0.0.0.0
  -Dsite.port           openzaly Netty port default:2021
  -Dhttp.address        openzaly Http address default:0.0.0.0
  -Dhttp.port           openzaly Http port default:8080
  -Dsite.admin.address  openzaly AdminSystem address default:127.0.0.1
  -Dsite.admin.port     openzaly AdminSystem port default:8081
  -Dsite.admin.uic      openzaly first uic for admin port default:000000
  -Dsite.baseDir        openzaly openzaly-server root dir default:./
  -Dgroup.members.count openzaly Max group member size default:100
```
### <h3 id="loginSite">**访问站点服务器**</h3> 

> * 生成自己的账户
> * 输入站点服务器地址
> * 首次登陆为管理员，邀请码：000000。 管理员登录之后，请在管理后台管理站点的基本信息
> * 将站点服务器地址分享给好友，app中添加为好友之后，就可以开始聊天了。


### <h3 id="installDocker">**一键安装Docker教程**</h3> 

快速安装基于Docker，以下是Docker的一键安装教程，**如果你已经拥有Docker环境，请跳过**。

* Linux
    * 直接通过yum、apt安装即可。
    * 或者访问：https://www.docker.com/community-edition#/download
* [Mac OSX](<https://store.docker.com/editions/community/docker-ce-desktop-mac>)
* [Windows Pro\Server](<https://store.docker.com/editions/community/docker-ce-desktop-windows>)

### <h3 id="docker">**基于Docker部署服务器**</h3> 

通过我们发布的Docker镜像，可以快速完成服务器搭建工作，整个过程只需两行命令。

> 如果你没有Docker环境，[一键安装Docker教程](#installDocker)


**1.请认准我们的官方docker镜像，无毒无害实时更新**

```
docker pull registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest
```

**2.服务器运行docker**
> baseAkaxin需要更改成你本地的目录，服务器的日志、图片、数据库将存储在这个位置。
> 
> 2021为默认的端口号，如果有需要修改，请修改第一个2021，第二个2021修改后，可能导致服务器地址无法正常访问
> 

**重要建议**  

*  更改baseAkaxin的目录位置，如果没有修改该目录，可能导致docker重启之后，会出现数据丢失的现象
> 

```
docker run -tid -v baseAkaxin:/akaxin -p 2021:2021 registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest
```

**3.运行以下命令，看到处于运行中的服务，代表程序运行成功，可以通过app访问站点服务器。**

```
 docker ps
```


使用过程若有任何问题，欢迎联系我们 feedback@akaxin.xyz
