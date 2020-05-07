## 配置Git

下载安装完Git后，在***File-->settings-->Version Control**下选择Git选项，在***Path to Git executable***中选择本地安装的git.exe文件，点击Test，成功会弹出Git版本信息，如下
![img](m_c26308fab52f920cbdb18ae96abc9464_r.png)
注意，下列***SSH executable***选项中，代表连接选项，通常我们使用简便一些Http的方式

![img](m_8ab80fbb32261334d0229da0c1d87ef5_r-1588818627618.png)

## 日常开发操作

### 拉取远程仓库代码

选择***File-->New-->Project from Version Control-->Git***，如下
![img](m_cd26d5f86124e471c9b9dd4becf83c39_r.png)
找到远程仓库地址，这里以我的Github为例，其他远程仓库类似，选择项目***clone or download***,选择http或ssh方式，复制地址，这里和idea中保持一致，选择http
![img](m_1877990939a86213515cd4cf06531b19_r.png)
然后切换至idea中，点击Test，这里我已经登录保存过，第一次需要填远程仓库的用户名密码，然后选择本地硬盘，如下
![img](m_9185d1fc5abce9c3aad7f7b73ffb33d1_r.png)
clone，等待片刻，弹出窗口，随便选择一个窗口打开即可，项目拉下来如下
![img](m_ee483ee71c6f11fb6c8bcb615803e7ad_r.png)
Idea右下角，代表分支，默认master分支，如下，***Local Branches***代表本地分支，***Remote Branches***代表远程分支，***New Branch***添加新的本地分支
![img](m_1e3740bbb65af2e826fe82486e14237f_r.png)

### 更新和提交
新增文件，test01.txt,弹出窗口提示，如下
![img](m_e263c754cc59cedc06f49314a758aef9_r.png)
该提示代表是否添加至暂存区，等同于git add命令，若选择add后，文件呈绿色，选择cancel则为红色，若此时为添加也可右键点击文件，选择***git-->add***
![img](m_019bb5c6eef4d6cd58e32ff0f248c43a_r.png)
工作完成后，选择idea工具栏中Git操作，如下
![img](m_1d813e51f902c4f19e0b839f611a7849_r.png)
项目目录中绿色新增的部分，为新增文件，下方红色为未添加到暂存区的，选择我们需要提交的文件，双击可查看新增或修改的内容，下方***Conmit Message***为提交的说明
![img](m_086a104e15bd701b6bbc55598a4689ea_r.png)
提交本地则选择Commit,提交远程选择***Commit And Push***，如下
![img](m_919e7cac07a79a948b539e61a7bb0f80_r.png)
![img](m_ff7f65ac8a549c9dd53d9028cc2b3ea9_r.png)
点击Push后弹出下列提示则成功
![img](m_2cf20ba910ffca25a5bba6730ccfb1f0_r.png)

### 切换分支及分支合并
选择右下角分支，切换至dev分支，自动会创建本地分支，如下
![img](m_87593e3c3fd12850eed0d57e14c44764_r.png)
切换完成后，此时添加test02文件，提交至本地即可，提交完成后，切换至本地master分支，此时项目中没有test02
![img](m_cc74e07e6d1f05bd345e4dd6d285e7d5_r.png)
左键点击dev分支，选择***Merge into Current***,如下
![img](m_a619eb29d83ce18e6b4b2103aac4b7e0_r.png)
现在看项目中,test02已经出来了，此时test02为白色，若想推送至远程，则需要继续push，右键项目，选择***GIT-->Repository-->Push***
![img](m_c605a03e807c166f2e2ee8c963913cbf_r.png)
然后检查需要提交的文件即可。
### 解决冲突
在远程仓库中修改readme.txt模拟他人提交
![img](m_d4c0c0dda00e55e49ca4eace8ad4437b_r.png)
本地也对readme.txt内容进行修改，添加内容“6666666666”，修改后文件呈蓝色，如下
![img](m_94ae29f97acce789b12c1db5a1494542_r.png)
若不进行更新直接提交，push时出现以下提示
![img](m_3f33d7523158ba424e39145625b901d1_r.png)
此时可以选择Cancel，执行Pull操作后再提交远程，也可以选择Merge，弹出Merge操作窗口，如下
![img](m_7c89e38a4b9360fc9b55cc1a08951ee2_r.png)
右方可以选择，接受你自己的，接受他人的，第三项则手动merge，选择手动Merge后，冲突的内容呈红色，左侧为本地，右侧远程仓库，中间则修改版本根据需要解决冲突即可
![img](m_486ecc885c4d93dd68fe33ce4c43b2ab_r.png)
**注：每次提交前都进行Pull操作可避免不必要的麻烦**