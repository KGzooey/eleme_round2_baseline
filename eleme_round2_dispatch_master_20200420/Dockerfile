FROM registry.cn-shanghai.aliyuncs.com/tcc-public/java:jdk_13.0.2
#FROM registry.cn-shanghai.aliyuncs.com/tcc-public/java:jdk_13.0.2
MAINTAINER annoymous

WORKDIR /data

# 根据需要打包，如果你依赖的base image自身没有带jdk，需要你手动打包进去，并且在run.sh中指定$JAVA_HOME
#ADD jdk11.tar.gz /data
# 根据需要打包
#ADD go1.14.1.linux-amd64.tar.gz /data

# 根据需要编译你自己的代码，如果是java/python代码，可以本地编译之后copy进image，否则的话，
# 需要在相关linux环境下编译之后copy进运行image，或者直接在下面RUN编译指令
COPY dispatch-demo/target/dispatch-demo.jar /data/

# 按照run.sh文件中说明，提供run.sh 脚本
COPY run.sh /data/

EXPOSE 8080

RUN chmod u+x /data/run.sh

CMD ["/bin/bash","/data/run.sh"]
