<div align=center><img alt="markdown-img-paste-20190724145947103.png" src="assets/markdown-img-paste-20190724145947103.png"></div>
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

	- [一 基本要求](#一-基本要求)
	- [准备工作](#准备工作)
	- [三 Glossary](#三-glossary)
		- [（一）ADC – 工业互联应用平台](#一adc-工业互联应用平台)
		- [（二）应用](#二应用)
		- [（三）环境](#三环境)
		- [（四）版本](#四版本)
		- [（五）应用实例](#五应用实例)
	- [四 迁移流程](#四-迁移流程)
		- [（一）注册账号](#一注册账号)
		- [（二）登录](#二登录)
		- [（三）申请成为开发者](#三申请成为开发者)
		- [（四）创建应用](#四创建应用)
		- [（五）创建环境](#五创建环境)
		- [（六）申请环境资源](#六申请环境资源)
		- [（七）封装并上传docker镜像](#七封装并上传docker镜像)
		- [（八）申请外网端口](#八申请外网端口)
		- [（九）编写部署配置文件](#九编写部署配置文件)
		- [(十) 使用开发者工具部署](#十-使用开发者工具部署)
		- [(十一)使用开发者工具升级部署](#十一使用开发者工具升级部署)
	- [五 服务间交互](#五-服务间交互)

<!-- /TOC -->
## 一 基本要求
  所迁移应用须能在linux下运行，且无法迁移Oracle等需要收费许可的组件。
## 准备工作
（详见迁移流程）

(1)	注册用户，平台地址: *https://adc.htres.cn/*

(2)申请成为开发者

(3)创建应用，获取到应用ID:
*https://adct.htres.cn/developer/application/list*

(4)创建环境，得到环境名称:
   *https://adct.htres.cn/environments/list*

(5)构建需要部署的项目，封装并上传docker镜像（linux版）

(6)管理员邮箱：<待添加>

(7)迁移流程以部署nginx为例
## 三 Glossary
### （一）ADC – 工业互联应用平台
工业互联应用平台，目的是打造一个以 工业应用 为核心的生态。涵盖应用的开发、运行、发布、购买、使用以及开发者社区 等应用全生命周期中的各个场景。
平台为工业应用生态构建提供基础，包括基础开发环境支持、运行环境支持、应用市场支持、微服务组件库支持。
平台是为APP提供服务，平台上的APP则是为工业企业提供服务。
### （二）应用
由开发者开发，可运行在adc平台，最终可以通过adc应用市场被客户购买使用的可执行软件（云化应用、组件库、本地应用程序）或远程服务（微服务）。
### （三）环境
环境就是运行应用所需要的硬件配置。所有注册用户，都可以任意的创建环境，自行管理环境的用途。比如，可以通过环境类型，对当前的环境做标记。当前支持将环境标记为生产、测试、开发环境，帮助用户区分使用场景。
	    创建环境后，无法立即使用。用户应按照自身需要，购买所需要大小的硬件配置。
### （四）版本
同一个应用可以发布多个不同版本。用户购买一个可执行软件类型的应用时，可以选择运行某个指定的版本。（当前未实现）
### （五）应用实例
无论是通过购买，还是通过开发者工具安装/部署的应用，都会对应一个应用实例。对应用的起停、升级、安装和卸载等操作，实际是作用于实例。同一个应用，可以被安装/部署到不同的环境中，多实例运行，以达到特定的效果。例如，同一个应用，被开发者同时部署到测试和生产环境中。测试环境中对新改动测试没问题之后，便可以发布新版。

---
## 四 迁移流程
### （一）注册账号
访问网站  *https://adc.htres.cn/*   点击首页右上角用户注册按钮，注册云网账号。
### （二）登录
使用之前注册的账号，登陆工业互联应用平台。
### （三）申请成为开发者
点击导航栏中的 开发者中心 按钮，进入开发者中心。点击 申请成为开发者 按钮，等待管理员审核通过之后，便可进入开发者中心。
<div align=center><img alt="markdown-img-paste-20190724145726216.png" src="assets/markdown-img-paste-20190724145726216.png"></div>

<center>申请开发者界面</center>

### （四）创建应用
进入开发者中心，点击左侧导航中的， 项目 -> 应用管理 进入到应用管理页面。然后创建新应用。

<div align=center><img alt="markdown-img-paste-20190724145710970.png" src="assets/markdown-img-paste-20190724145710970.png"></div>

<center>创建应用界面</center>

其中对于应用类型，用户购买后需要自行安装到服务器上的应用，选择“云化应用”。用户无需安装，类似于B/S架构，可直接访问的应用，选择“第三方SaaS”。
对于应用详情，其内容支持html标签。
### （五）创建环境
点击左侧导肮中的 环境管理 ，进入到环境管理页面。点击购买环境。
<div align=center><img alt="markdown-img-paste-20190724145649290.png" src="assets/markdown-img-paste-20190724145649290.png"></div>

<center>购买环境界面</center>

其中对于默认CPU配额为部署到该环境下的应用可默认能分配到的CPU的个数，默认内存配额为部署到该环境下的应用，默认能分配到的内存的大小。
### （六）申请环境资源
环境购买之后，按照自身需要，购买所需要大小的硬件配置。等待管理员审核之后，便可使用该环境，在环境中部署应用。
### （七）封装并上传docker镜像
示例中使用nginx官方镜像 *https://hub.docker.com/_/nginx*

具体docker镜像封装方法，请参考docker官方文档: *https://docs.docker.com/* 。
后期会提供特定场景下的demo，作为参考模板。
### （八）申请外网端口
若程序需要通过外网访问，请联系管理员申请外网端口。因护网行动，新增端口无法直接使用，需要提交工单。
### （九）编写部署配置文件
&#8195;&#8195;例如配置文件名为deploy.yaml，内容如下：<br>
apiVersion: apps/v1 #  for k8s versions before 1.9.0 use apps/v1beta2  and before 1.8.0 use extensions/v1beta1<br>
kind: Deployment<br>
metadata:<br>
&#8195;name:  nginx #应用名<br>
&#8195;namespace: test #环境名<br>
spec:<br>
&#8195;selector:<br>
&#8195;&#8195;matchLabels:<br>
&#8195;&#8195;app: nginx #应用名<br>
&#8195;&#8195;tier: backend<br>
&#8195;replicas: 1<br>
&#8195;template:<br>
&#8195;&#8195;metadata:<br>
&#8195;&#8195;&#8195;labels:<br>
&#8195;&#8195;&#8195;app: nginx #应用名<br>
&#8195;&#8195;&#8195;tier: backend<br>
&#8195;&#8195;spec:<br>
&#8195;containers:<br>
&#8195;- name: nginx #应用名<br>
&#8195;&#8195;image: nginx:latest #镜像地址<br>
&#8195;&#8195;imagePullPolicy: Always<br>
ports:<br>
&#8195;&#8195;\- containerPort:80

---
外网访问<br>
apiVersion: v1<br>
kind: Service<br>
metadata:<br>
&#8195;name: nginx-service-online #外网服务名<br>
&#8195;namespace: test #环境名<br>
&#8195;labels:<br>
&#8195;&#8195;app: nginx #应用名<br>
&#8195;&#8195;tier: backend<br>
spec:<br>
 &#8195;#if your cluster supports it, uncomment the following to automatically create<br>
 &#8195;#an external load-balanced IP for the frontend service.<br>
&#8195;type: LoadBalancer<br>
&#8195;loadBalancerIP: 106.74.152.35 #外网IP<br>
&#8195;ports:<br>
&#8195;- name: http<br>
&#8195;&#8195;port: 11111 #外网端口<br>
&#8195;&#8195;targetPort: 80<br>
      &#8195;&#8195;protocol: TCP<br>
    &#8195;selector:<br>
      &#8195;&#8195;app: nginx #应用名<br>
&#8195;&#8195;tier:backend<br>
&#8195;&#8195;以上是一个简单的部署配置模板，开发者只需将模板中字符串nginx替换为自己的应用名（必须为小写字母、数字、减号的组合，且以字母开头），将环境名替换为自己创建的环境名，将镜像地址替换为所要部署的应用镜像地址以及将外网IP/端口替换为自己所申请的外网端口即可。

   ---

### (十) 使用开发者工具部署
需要用到开发者工具：
[adc-windows-x86.64.zip](https://code.htres.cn/jitianyu/adc-cli/uploads/97591a6130d3b27dc6c396e1b4a7fe29/adc-windows-x86_64.rar)
---
[adc-linux-amd64.zip](https://code.htres.cn/jitianyu/adc-cli/uploads/3dd502e80e86accc21fa38e94a1c71ff/adc-linux-amd64.rar)
---
[adc.properties](https://code.htres.cn/jitianyu/adc-cli/uploads/87c8cb48cd5b719a61e67b8288c45c78/adc.properties)
---
详细步骤如下：
  1. 根据所使用操作系统，选择对应的文件进行解压。
  2. 将解压出来的文件与adc.properties 放到同一文件夹下。
  3. 为开发者工具添加PATH，或者将之前编写的部署配置文件与开发者工具放到同一目录下。
  4. 执行登录命令adc.exe login，需要用到之前注册的平台账号信息。
  5. 执行安装命令adc.exe install，需要用到部署配置文件、创建应用所获取到的ID以及指定RELEASE NOTE、版本号、实例名。
---
执行以上步骤后，会在实例管理页面看到新安装的实例。
<div align=center><img alt="markdown-img-paste-20190724145549976.png" src="assets/markdown-img-paste-20190724145549976.png"></div>

<center>实例安装界面</center>

***
<div align=center><img alt="markdown-img-paste-20190724145537190.png" src="assets/markdown-img-paste-20190724145537190.png"></div>

<center>实例管理界面</center>

---
<div align=center><img alt="markdown-img-paste-2019072414552227.png" src="assets/markdown-img-paste-2019072414552227.png"></div>
<center>实例状态界面</center>
并可以通过外网地址访问刚才部署的应用。无可用端口，图片暂时无法提供。

***

### (十一)使用开发者工具升级部署

 执行安装命令后，会默认创建一个版本。（应用管理->目标应用卡片->版本管理按钮）
 <div align=center><img alt="markdown-img-paste-20190724145228962.png" src="assets/markdown-img-paste-20190724145228962.png"></div>

---
若想在此版本基础上继续改进程序，可使用升级命令。重新上传镜像/修改部署配置文件后，调用*adc.exe upgrade* 命令即可：
<div align=center><img alt="markdown-img-paste-20190724145054583.png" src="assets/markdown-img-paste-20190724145054583.png"></div>

## 五 服务间交互
  在部署配置文件中，加入内网服务配置，并重新部署后。便可以在其它部署在平台的应用中，通过该形式访问：
  *http://nginx-service:8080*

内网访问<br>
apiVersion: v1<br>
kind: Service<br>
metadata:<br>
    &#8195;name: nginx-service #内网服务名<br>
    &#8195;namespace: test<br>
    &#8195;labels:<br>
      &#8195;&#8195;app: nginx<br>
      &#8195;&#8195;tier: backend<br>
spec:<br>
    &#8195;type: ClusterIP<br>
    &#8195;ports:<br>
    &#8195;- name: http<br>
      &#8195;&#8195;port: 8080<br>
      &#8195;&#8195;targetPort: 80<br>
      &#8195;&#8195;protocol: TCP<br>
    &#8195;selector:<br>
      &#8195;&#8195;app: nginx<br>
      &#8195;&#8195;tier: backend<br>
