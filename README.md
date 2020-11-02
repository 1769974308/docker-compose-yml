# docker-compose-yml

#### 介绍
用于定义和运行多容器Docker应用程序的工具，通过Compose,可以使用YML文件来配置应用程序需要的所有服务，然后，使用一个命令，就可以从YML文件配置中创建并启动所有服务，Docker Compose将所管理的容器分为三层，工程、服务及容器。docker-compose.yml中定义所有服务组成了一个工程，services节点下即为服务，服务之下为容器。容器与容器直之间可以以服务名称为域名进行访问，比如可以通过jdbc:mysql://db:3306这个地址来访问db这个mysql服务。


#### 安装教程

1. 发行版本地址：https://github.com/docker/compose/releases
2. 下载稳定版本：$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
3. 可执行权限应用于二进制：$ sudo chmod +x /usr/local/bin/docker-compose
4. 创建软链接：$ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
5.  测试：$ docker-compose --version

#### 使用说明

1.创建并启动配置的容器:docker-compose -f   xxx.yaml up
2.指定服务名称来启动:docker-compose -f xxx.yaml up  服务名1 服务名2
3.后台全部启动:docker-compose -f  xxx.yaml up -d
4.启动单个服务：docker-compose -f xxx.yaml start 服务名
5.停止单个服务：docker-compose -f xxx.yaml stop 服务名
6.重启单个服务：docker-compose  -f xxx.yaml restart 服务名
7.列表所有容器: docker-compose -f xxx.yaml ps
8.拉取服务依赖镜像： docker-compsoe -f xxx.yaml pull
9.设置指定服务运行的容器个数：docker-compose scale web=3 db=2




