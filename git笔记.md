# git基础

### 1.使用git前的配置

````
配置提交人姓名：git config --global user.name 提交人姓名
配置提交人邮箱：git config --global user.email 提交人邮箱
查看git配置信息：git config --list （分别查看 git config user.name || git config user.email）
````

### 2. git基本的使用

#### 创建一个仓库

 ```
 git init
 ```

#### 查看文件状态

````
git status
````

#### 添加到暂存仓库

````
git add 文件列表
````

#### 提交到本地创库

````
git commit -m '提交的信息'
````

#### 查看提交记录

````
git log //使用git log --oneline 缩减到一行显示
````

#### 设置版本号

````
git tag v1.0.0
git checkout v1.0.0 
注：版本号可以自定义
````

#### 回滚版本

```
git reset --hard 版本号
```

#### 查看回滚之后提交的版本

````
git reflog
````

####  回滚还没修改状态

````
git status
git checkout -- index.html 
````

####  回滚到还没add到暂存仓库状态

````
git add .
git status
git reset head index.html
````



#### 总结

````
git init
git add
git commit
git log
git reflog
git reset --hard 版本号git
git reset head 
````



### 3. 分支

实现多人开发，相互不影响

#### 查看已有分支

````
git branch
````

 #### 创建一个分支

````
git checkout -b 分支名称
git branch 分支名称
注:使用checkout -b'分支名'   会创建并进入分支
   branch'分支名'           创建分支不会进入分支
````

#### 切换分支

````
git branch
git checkout 分支名称"
````

#### 合并分支

````
git merge 分支名称
````

#### 删除分支

````
git branch -d 分支名称
git branch
````

#### 合并冲突问题

提示以下的问题就是：合并冲突

![image-20220303200926752](C:\Users\鸢泽童话\AppData\Roaming\Typora\typora-user-images\image-20220303200926752.png)

手动修改：找到修改的文件，进行手动修改

#### 总结

````
git branch            //查看分支
git branch 分支名      // 创建分支
git checkout 分支名     //切换分支
git merge 要合并的分支   //分支合并(可能产生冲突)
注意：切换分支再合并分支

git branch -d 分支名称  //删除分支
````



### 4. 工作流

项目开始创建2个分支（master、dev），一个稳定版，一个dev测试版，开发的基于dev分支上经行开发，master用来合并稳定分支



### 5. 远程仓库

#### 连接远程仓库

```
git remote add origin 创库地址
```

####  添加一个分支到远程创库

```
git push -u origin 分支名
```





