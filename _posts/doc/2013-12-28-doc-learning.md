---

layout: doc

title: Hybrid framework

description: 本文介绍了WHF framework的开发文档	。
category: doc

---

![Mou icon](/images/Mou_128.png)


	
##3.开发文档	
### 3.1 使用流程
下图是H5和Native调用的流程图

![调用流出](/images/process.png)

	1. App进入H5模块页面，LoadWebView;
	2. Webview加载完成(WebViewDidFinishedLoad)，通过app.callback()回调tagname=web_view_finish_load给H5页面;
	3. H5页面可以调用JS Lib中的所有API，例如app_login();
	4. JS Lib会通过plugin方式调用native的login函数;
	5. native的login函数执行完成，回调给JS Lib;
	6. JS Lib将用户登录的数据回调给H5;
说明：由于JS Lib函数调用的时候，H5页面可能尚未加载完成，因此必须等收到web_view_finish_load的回调之后;
### 3.2 全局数据结构

app.callback(jsonParam)函数<br/>

app 主动调用和回调H5页面，都是通过该函数完成。因此，`所有的H5页面，都需要实现该函数`。<br/>	
jsonParam为JSON对象类型,其内部参数格式如下:
	
	{
		tagname:"xxxxx",	
		param:{key1:"xxx",key2:"xxxa"}
	}	
	//tagname:参数类型为字符串, 回调的事件名,不能为空;
	//param: 参数类型为JSON对象, 调用/回调给H5的数据,该字段允许为空;	

### 3.3.	数据交互

总共分2部分，app调用H5，H5调用App

#### 3.3.1.	App调用H5

App调用H5分为两种，App主动调用H5，App回调H5.

`App主动调用H5`

A.标识H5页面状态的固定回调

	1. H5页面加载完成，通知H5;
	2. H5页面激活，从后台切入前台，通知H5;
	3. H5页面加载完成后，切换到其它页面之后，回退回来，再次显示时候，通知H5;
	
	
B.H5页面顶部导航栏上的按钮事件

H5页码的顶部导航栏是由native实现，导航栏上面的按钮，文字，均由H5控制(有JS函数可以设置顶部导航栏内容)，因此顶部导航栏的按钮也算是H5页面的一部分，顶部按钮事件也应由H5控制； 
	
	1.左侧返回按钮
	用户点击返回，app会调用H5的app.callback({tagname:'back'}), H5返回true，则使用H5的返回，否则app会处理该返回事件；
	2.右侧内容
	右侧按钮点击，app会调用H5的app.callback({tagname:'xxxx'}),tagname为H5设置的该按钮的属性;


`App回调H5`

	H5调用JS Lib的函数之后，如果有数据需要返回给H5的，app会通过调用H5的app.callback({tagname:'xxxx', param:{key1:"xxxx", key2:"xxxxx"}}),将数据返回给H5

	具体的各个API回调的参数格式，请参考后文[API文档];
	
####3.3.2.	H5调用App
	1.H5调用JS Lib中的API
		a.通用功能，H5页面调用JS库中的相关JS API. 具体API定义参考后面的API手册;
		b.业务相关, JS Lib中对部分有返回值的业务模块的API进行封装，例如会员登录/注册，支付业务;	
	
	2.H5拼装ctrip:协议的URL Schema做跳转
	   通过URL schema方式调用,拼装完成后，调用JS Lib里面的CtripUtil.app_open_url()函数,跳转到各个app页面。
	   具体的URL Schema定义列表参考后面的URL Schema手册；

	
### 3.4.	调试
下文以上面demo中为例，描述了怎样将该webapp放入到app中调试<br/>

<ul>
<li>1.点击安装<a href="itms-services://?action=download-manifest&url=http://210.13.100.191:7001/qunit/cw_install.plist">携程旅游App开发版</a></li>
<li>2.将html文件存储为home.html. 然后将home.html, bridge.js放入文件夹demo,使用zip压缩demo文件夹，得到demo.zip；</li>
<li>3.iOS通过<a targe="_blank" href="http://support.apple.com/kb/HT4094?viewlocale=zh_CN&locale=zh_CN">iTunes文件共享</a>将demo.zip文件copy到携程旅行的文稿目录;</li>
<img src="/images/file_sharing.jpg" width="620"></img>
<li>4.进入H5开发设置页面。步骤：进入用车－》点击底部H5设置按钮即可</li>
<li>5.在下图的页面中，输入新增模块的相对路径，如zip包解压之后为demo，首页地址为demo/home.index.html</li>
<img src="/images/input.jpg"></img>
<li>6.点击新加入的测试入口进入测试；</li>
<img src="/images/input_done.jpg"></img>
<li>7.测试页面内容显示如下；</li>
<img src="/images/demo.png"> </img>
</ul>	

在H5开发设置页面里面，还有2个按钮。<br/>
1.更新日志，点击可以查看webapp自动更新的每一个步骤；<br/>
2.开发首页，即该开发站点的链接，内部有JS Lib自动化测试入口和手动测试入口；<br/>

![debug_log](/images/debug_2.jpg)

上图显示了日志查看功能；
