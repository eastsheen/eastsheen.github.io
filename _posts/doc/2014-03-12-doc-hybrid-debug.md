---

layout: doc

title: Ctrip Hybrid App debug

description: 本文介绍了Ctrip Hybrid App debug方式。
category: doc

---


![Mou icon](/images/Mou_128.png)


##How to debug in Ctrip App?


###1. 进入H5开发设置页面，打开本地Debug开关;
![a](/images/hybrid_debug/open_debug.PNG)

###2. 通过iTunes File Sharing拷贝开发的Webapp目录;
![b](/images/hybrid_debug/webapp.png)

`NOTE:请直接zip webapp文件夹；`
![c](/images/hybrid_debug/webapp_a.png)

###3.进入App里面的H5模块，例如：用车模块，此时webapp.zip会自动解压;

![d](/images/hybrid_debug/webapp_b.png)

###4. 准备lipin.zip文件夹；

![e](/images/hybrid_debug/lipin.png)

###5. 将lipin.zip通过iTunes File Sharing拷贝到Webapp目录；
![f](/images/hybrid_debug/lipin_a.png)

###6. 在H5开发设置页面，添加lipin入口；
![g](/images/hybrid_debug/lipin_b.PNG)

`NOTE:通过iTunes File Sharing拷贝的zip文件夹和新增的测试入口名字必须一致；
例如此处，添加的是lipin.zip文件夹，添加的测试入口为/lipin/index.html`

###7.添加完成后，可以看到lipin目录已经解压到webapp目录，如下图；
![h](/images/hybrid_debug/done.png)

###8. 开始Debug