#依赖环境
FROM centos
RUN yum install wget -y \
	&& wget https://nodejs.org/dist/v8.11.3/node-v8.11.3-linux-x64.tar.xz \
	&& tar xvJf node-v8.11.3-linux-x64.tar.xz \
	&& ln -s /node-v8.11.3-linux-x64/bin/node /usr/local/bin/node \
	&& ln -s /node-v8.11.3-linux-x64/bin/npm /usr/local/bin/npm \
	&& yum install -y git \
	&& npm -v


#拷贝jar文件
COPY ./vue-element-admin vue
WORKDIR ./vue
RUN ls -al \
	&& npm config set registry https://registry.npm.taobao.org \
	&& npm set sass_binary_site=https://npm.taobao.org/mirrors/node-sass/ \
	&& npm install --unsafe-perm --save-dev
	
ENTRYPOINT [ "npm", "run", "dev" ]
EXPOSE 9527	

