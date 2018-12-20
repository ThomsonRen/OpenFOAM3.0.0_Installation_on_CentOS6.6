# OpenFOAM3.0.0_Installation_on_CentOS6.6
本文提供作者在课题组的超算系统上（非root用户）安装OpenFOAM3.0.0的方法

## 1.下载源码包
在OpenFOAM官网下载OpenFOAM-3.0.0.tgz 和 ThirdParty-3.0.0.tgz两个源码包 
```
https://openfoam.org/download/3-0-0-source/ 
```
将下载的文件放在个人目录的OpenFOAM下（如果没有OpenFOAM文件夹就新建一个），作为OpenFOAM3.0.0的安装目录。
例如，我的用户名为rentongxin,对应的安装目录就是```/public/home/rentongxin/OpenFOAM```

然后，进入到安装目录下(```/public/home/rentongxin/OpenFOAM```)，对压缩文件解压缩，即可得到后续安装所需的源码包
```
  tar -xzf OpenFOAM-3.0.0.tgz  
  tar -xzf ThirdParty-3.0.0.tgz
```
## 2.修改bashrc文件
正式安装之前，需要修改环境变量。

首先，进入到```/OpenFOAM/OpenFOAM-3.0.0/etc```文件夹下，利用vi打开bashrc文件
```
vi bashrc
```
此时我们会在终端看到bashrc文件的内容，我们需要修改的主要在前几行（注意看前几行英文对应的意思，大概意思是：用户可以通过前几行这些语句进而修改环境变量的，之后的语句不推荐修改，除非你知道它们在做什么）
```
#------------------------------------------------------------------------------

export WM_PROJECT=OpenFOAM
export WM_PROJECT_VERSION=3.0.0

################################################################################
# USER EDITABLE PART: Changes made here may be lost with the next upgrade
#
# either set $FOAM_INST_DIR before sourcing this file or set
# 'foamInstall' below to where OpenFOAM is installed
#
# Location of the OpenFOAM installation
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#foamInstall=$HOME/$WM_PROJECT
# foamInstall=~$WM_PROJECT
# foamInstall=/opt/$WM_PROJECT
foamInstall=/public/home/rentongxin/$WM_PROJECT
# END OF (NORMAL) USER EDITABLE PART
################################################################################
```
首先，将```#foamInstall=$HOME/$WM_PROJECT```那行注释掉，然后自定义用户的安装绝对路径，例如对于我的用户来说路径为：
```/public/home/rentongxin/$WM_PROJECT```

然后，注释掉原有的```FOAM_INST_DIR```声明语句（在第50-60行附近，因为我对源文件做过修改，具体数据忘记了）
```
: ${FOAM_INST_DIR:=$foamInstall}; export FOAM_INST_DIR
```

最后，在刚才的```foamInstall```那行之下另起两行，加入一下两行代码，声明新的```FOAM_INST_DIR```绝对路径（注意按照自己的用户名就行修改，此处以rentongxin为例）
```
FOAM_INST_DIR=/public/home/rentongxin/$WM_PROJECT
export FOAM_INST_DIR
```
## 3. 修改用户环境变量
进入用户主文件夹
```
cd ~
```
使用vi打开隐藏文件```.bashrc```






