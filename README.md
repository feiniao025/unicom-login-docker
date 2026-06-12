一键部署命令，使用您构建的 GHCR 镜像，映射端口 5702，并设置容器自动重启。

bash
docker run -d \
  --name unicom-login \
  --restart unless-stopped \
  -p 5702:5702 \
  ghcr.io/feiniao025/unicom-login:latest
命令解释：

-d：后台运行

--name unicom-login：容器名称

--restart unless-stopped：自动重启（除非手动停止）

-p 5702:5702：将宿主机 5702 端口映射到容器 5702 端口

ghcr.io/feiniao025/unicom-login:latest：镜像地址

使用说明：

部署后访问 http://你的服务器IP:5702/login.php 即可打开登录页面。

如需停止容器：docker stop unicom-login

如需删除容器：docker rm unicom-login

如需查看日志：docker logs -f unicom-login

如果服务器已经登录过 GHCR，无需额外登录；如果未登录且镜像为私有，需要先执行：
