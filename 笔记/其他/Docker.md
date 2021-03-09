## Docker 命令

| 镜像命令          | 作用                                                      |
| ----------------- | --------------------------------------------------------- |
| **docker images** | 列出本地镜像 **-a**列出本地所有的镜像,**-q**只显示镜像 ID |
| **docker push**   | 将本地的镜像上传到镜像仓库                                |
| **docker search** | 查找镜像                                                  |
| **docker pull**   | 拉取或更新镜像                                            |
| **docker rmi**    | 删除镜像                                                  |
| **docker login**  | 登陆到一个 Docker 镜像仓库                                |
| **docker logout** | 退出 Docker 镜像仓库                                      |
| **docker tag**    | 标记本地镜像,将其归入某一仓库                             |
| **docker save**   | 将指定镜像保存成 tar 归档文件                             |
| **docker import** | 从归档文件中创建镜像                                      |
| **docker build**  | 创建镜像                                                  |

| 容器命令               | 作用                                |
| ---------------------- | ----------------------------------- |
| **docker run**         | 创建新的容器并运行, **-d** 后台运行 |
| **docker rm**          | 删除容器                            |
| **exit**               | 退出并停止容器                      |
| **<kbd>Ctrl+P+Q<kbd>** | 退出不停止容器                      |
| **docker start**       | 启动容器                            |
| **docker stop**        | 停止容器                            |
| **docker restart**     | 重启容器                            |
| **docker kill**        | 杀掉运行中的容器                    |
| **docker pause**       | 暂停容器中所有进程                  |
| **docker unpause**     | 恢复容器中所有进程                  |
| **docker create**      | 创建新的容器但不启动                |
| **docker exec**        | 在运行的容器中执行命令              |
| **docker top**         | 查看容器中运行的进程信息            |
| **docker logs**        | 获取容器的日志                      |
| **docker ps**          | 列出容器                            |
| **docker commit**      | 从容器创建一个新的镜像              |

| DockerFile 构建镜像 | 作用                                      |
| :-----------------: | ----------------------------------------- |
|        FROM         | 构建镜像的基础镜像                        |
|         RUN         | 执行后面的命令行命令,在 docker run 时运行 |
|         CMD         | 和 RUN 类似,在 docker build 时运行        |
|        COPY         | 从目录中复制文件或目录到容器里指定路径    |
|       VOLUME        | 定义匿名数据卷,会自动挂载到匿名卷         |
|         ENV         | 设置环境变量                              |
