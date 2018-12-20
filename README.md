# OpenFOAM3.0.0_Installation_on_CentOS6.6
本文提供作者在课题组的超算系统上（非root用户）安装OpenFOAM3.0.0遇到的问题和解决方法

## 1.下载源码和第三方库
在OpenFOAM官网下载OpenFOAM-3.0.0.tgz 和 ThirdParty-3.0.0.tgz两个源码包 

下载地址：https://openfoam.org/download/3-0-0-source/ 

将下载的文件放在个人目录的OpenFOAM下（如果没有OpenFOAM文件夹就新建一个），作为OpenFOAM3.0.0的安装目录。
例如，我的用户名为rentongxin,对应的安装目录就是：/public/home/rentongxin/OpenFOAM


tar -xzf OpenFOAM-3.0.0.tgz 
tar -xzf ThirdParty-3.0.0.tgz
