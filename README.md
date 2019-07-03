# docker-miscellaneous
docker与skywaiking agent 与时区的配合，打成一个基础镜像


使用时请将base/java:8替换成使用Dockerfile-base 打成的镜像包上传的仓库路径地址


#这个是使用的基础镜像包，根据实际情况改变你的基础镜像
FROM java:8
LABEL author=zygfengyuwuzu@sina.com describe=打包基础镜像层，包括时区的改变时区为东八区，skywalking6.0agent包
#copy skywalking的agent 代理相关包到镜像中，路径可以看情况设定
COPY agent/ /usr/local/skyagent/

运行

docker run -p 11005:11005 -e agent_servicename=mytest -e 'JAVA_OPTS=-Xmx256m -Xms256m' youimage:version
