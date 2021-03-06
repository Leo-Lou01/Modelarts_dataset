# 使用Modelarts标注、生成无人车路标检测数据集
2022.04.13 lzh  

## step1 注册华为云账号
网址：https://www.huaweicloud.com/  
  
## step2 登陆账号并返回华为云官网
![avatar](/readme/huaweicloud_official_website.png)  
  
## step3 点击右上，搜索modelarts，点击 控制台 选项进入
![avatar](/readme/modelarts_search.png)  
  
## step4 上方搜索 obs 点击进入如下界面
![avatar](/readme/obs.png)  
  
## step5 点击 创建桶 修改相关设置，创建桶
[注] 区域需为 华北-北京四  

## step6 返回Modelarts界面
网址：https://console.huaweicloud.com/modelarts/?region=cn-north-4#/dashboard  
  
## step7 点击左侧 菜单栏->数据管理->数据集
![avatar](/readme/2dataset.png)  
  
## step8 点击创建数据集，进入如下界面，进行相应修改，点击 创建
![avatar](/readme/dataset_settings.png)  
需修改项目：  
&emsp;名称 <自定义>  
&emsp;标注场景 图片  
&emsp;标注类型 物体检测  
&emsp;输入位置 obs中存放待标注图片的位置  
&emsp;输出位置 obs中存放标注后数据集的位置  
&emsp;添加标签集 obs中存放待标注图片的位置  
&emsp;添加标签集  
&emsp;打开 启用团队标注
  
## step9 标注
点击相应数据集，进入数据集概览，点击 全部  
![avatar](/readme/marks1.png)  
点击 添加图片，并导入本地（或obs上）待标注图片  
上传成功后，可以看见界面中有导入图片的概览图，单击图片开始标注  
[注] 标注尽量不含背景，只含特征物，如下图所示  
![avatar](/readme/marks2.png)  
完成所有图片的标注

## step10 发布当前版本数据集
![avatar](/readme/publish1.png)  
数据切分：切分train和test
点击 确定 完成数据集版本的发布

## step11 label存储位置
找到数据集输出地址，如下图所示  
![avatar](/readme/outputloc.png)  
.xml存储位置：数据集输出地址/数据集名称-xxx/annotation/V00x（对应版本）/annotations  
下载方式：下载OBS-Browser+批量下载文件，在线方式不能批量下载。  
