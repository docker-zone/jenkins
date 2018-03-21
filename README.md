# 前言
	jenkin安装方法

# 使用指南
	首先建立数据卷容器
	docker run --name jenkins_volume -v /app/docker/tools/jenkins:/var/jenkins_home alpine:3.7
	然后运行jenkins容器
	docker run -d --name jenkins -u root --volumes-from jenkins_volume -p 8080:8080 -p 50000:50000 jenkins:alpine
	备注：确保jenkins用户有/var/jenkins_home文件夹的使用权限，这里使用-u root指定了root用户的权限。