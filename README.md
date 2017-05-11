# docker-zentao
此文件用于构建一个禅道的镜像，可用于项目管理

大体步骤
1、下载zentao压缩包

2、解压执行运行命令

3、data目录挂载到宿主机上

4、执行如下指令，在docker机上完成如下几个步骤
	1）删除存在的容器
	2）启动新容器（通过挂载卷的形式挂载新的war包）


#推荐启动命令
docker run -d \
-p 8085:8080 \
-v /etc/localtime:/etc/localtime:ro \
-v /opt/docker/storage/zentao/data:/opt/zbox/data \
-e TZ="Asia/Shanghai" \
--name zentao \
--restart always \
wanxin/docker-zentao