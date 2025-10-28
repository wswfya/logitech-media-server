# LMS容器仓库
基于Docker Hub镜像`toertel/logitech-media-server`构建的LMS容器配置。
## 使用方式
1. 克隆本仓库：`git clone https://github.com/wswfya/logitech-media-server.git`
2. 构建镜像：`docker build -t lms-local .`
3. 启动容器：`docker run -d --name lms-server --net=host -v ./config:/srv/squeezebox -v ./music:/music lms-local
