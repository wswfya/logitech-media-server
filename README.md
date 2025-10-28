# LMS容器仓库
基于Docker Hub镜像`toertel/logitech-media-server`构建的LMS容器配置。仅拉去镜像到ghcr.io方便使用
## 使用方式
1. 克隆本仓库：`git clone https://github.com/wswfya/logitech-media-server.git`
2. 构建镜像：`docker build -t lms-local .`
3. 启动容器：`docker run -d --name lms-server --net=host -v ./config:/srv/squeezebox -v ./music:/music lms-local
      ghcr.io/wswfya/logitech-media-server：latest --platform linux/arm64
# LMS 镜像拉取命令（多架构适配）

# 1. 先确认宿主机架构（执行以下命令）
uname -m 
# 输出对应架构：x86_64→amd64；armv7l→armv7；aarch64→arm64

# 2. 按架构选择拉取命令（--platform 后为架构后缀）
# amd64 架构（x86_64设备）：后缀 linux/amd64
docker pull ghcr.io/wswfya/logitech-media-server:latest --platform linux/amd64

# armv7 架构（老旧ARM设备）：后缀 linux/arm/v7
docker pull ghcr.io/wswfya/logitech-media-server:latest --platform linux/arm/v7

# arm64 架构（aarch64设备）：后缀 linux/arm64
docker pull ghcr.io/wswfya/logitech-media-server:latest --platform linux/arm64

# 3. 通用启动命令（拉取完成后执行）
docker run -d --name lms-server --net=host -v ./config:/srv/squeezebox -v ./music:/music ghcr.io/wswfya/logitech-media-server:latest
