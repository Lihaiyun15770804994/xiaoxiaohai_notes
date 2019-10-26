## Git踩过的错以及解决办法:

### 1.使用git的时候一个本地仓库关联多个远程仓库报错:

```
To https://github.com/Lihaiyun15770804994/haiyub.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/Lihaiyun15770804994/haiyub.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

```

**问题原因**：远程库与本地库不一致造成的，在hint中也有提示把远程库同步到本地库就可以了。

**解决办法**：使用命令行：

git pull --rebase origin master

该命令的意思是把远程库中的**更新合并**到（**pull=fetch+merge**）本地库中，**–-rebase**的作用是取消掉本地库中刚刚的commit，并把他们**接到**更新后的版本库之中。出现如下图执行pull执行成功后，可以成功执行git push origin master操作。

![img](https://img-blog.csdnimg.cn/20190103111754961.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpZXRpbWUxOTQz,size_16,color_FFFFFF,t_70)

**图形描述问题发生的原因及解决办法**：

**1**. 发生问题时候的状态：

![img](https://img-blog.csdnimg.cn/20190103165316596.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpZXRpbWUxOTQz,size_16,color_FFFFFF,t_70)

**2**. 执行 git pull -–rebase origin master 操作，意为先取消commit记录，并且把它们**临时**保存为补丁(patch)(这些补丁放到”.git/rebase”目录中)，之后同步远程库到本地，最后合并补丁到本地库之中。

![img](https://img-blog.csdnimg.cn/20190103165623544.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpZXRpbWUxOTQz,size_16,color_FFFFFF,t_70)

**3**. 最后把本地库push到远程库当中，使本地与远程仓库保持一致。

![img](https://img-blog.csdnimg.cn/2019010316575311.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpZXRpbWUxOTQz,size_16,color_FFFFFF,t_70)



### 2.关于一个本地仓库关联多个远程仓库,远程仓库的名字要改:

git add remote '远程仓库名'(如果已存在origin,不要写origin,origin是关联第一个远程仓库的时候用的,关联其他的远程仓库的时候用其他的名字,不然会报,远程仓库已存在的错误;

想要查看当前本地仓库关联了哪些远程仓库:
git remote -v$ git remote -v
origin  https://github.com/Lihaiyun15770804994/first_test.git (fetch)
origin  https://github.com/Lihaiyun15770804994/first_test.git (push)
originlab       https://github.com/Lihaiyun15770804994/haiyub.git (fetch)
originlab       https://github.com/Lihaiyun15770804994/haiyub.git (push)

### 3.git删除一个关联的远程库:

git remote rm '远程库的名称'

