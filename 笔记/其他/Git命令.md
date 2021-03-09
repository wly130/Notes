# Git 常用命令

- **在网址前面添加  `https://htmlpreview.github.io/?`  就可以查看网页效果图了**


| 命令                       | 作用                                          |
| -------------------------- | --------------------------------------------- |
| **git init**               | 创建一个 git 仓库,在当前目录生成一个.git 文件 |
| **git add *FileName***     | 把文件添加到缓冲区                            |
| **git add .**              | 把所有文件添加到缓冲区                        |
| **git rm FileName**        | 删除文件                                      |
| **git commit -m "说明"**   | 提交缓冲区的所有修改到仓库                    |
| **git status**             | 查看本地库的状态, add 过为绿色                |
| **git diff Filename**      | 比较文件修改前后的差异                        |
| **git log**                | 查看日志                                      |
| **git reset**              | 版本回退                                      |
| **git reset --hard HEAD^** | 回退到上一个版本                              |
| **git reflog**             | 查看命令历史                                  |
| **git remote -v**          | 显示所有远程仓库                              |
| **git remote add url**     | 关联一个远程仓库                              |
| **git remote set 新url**   | 修改关联的远程仓库                            |
| **git remote remove url**  | 删除关联的远程仓库                            |
| **git remote show 仓库名** | 显示远程仓库信息                              |
| **git push origin master** | 上传代码到 Github 上                          |
| **git pull origin master** | 从 Github 上下载代码                          |
| **git branch**             | 查看本地所有的分支                            |
| **git branch -a**          | 查看远程所有的分支                            |
