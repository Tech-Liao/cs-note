# docker问题
docker create命令创建容器,无法通过docker start启动.
因此,还是通过docker run命令来创建容器.
docker run是用来创建容器,所以已经创建好的容器通过docker start和docker exec/docker attach来进入容器.
否则,docker run会重复创建容器
