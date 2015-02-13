---

layout: doc

title: 手动测试

description: manual test 
category: doc

---


 <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Helvetica; min-height: 16.0px}
    p.p3 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Helvetica}
    li.li2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Helvetica; color: #2567e8}
    li.li3 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Helvetica}
    span.s1 {text-decoration: underline}
    ul.ul1 {list-style-type: disc}
  </style>

 <script type="text/javascript" src="/code/bridge.js"></script>

  <script type="text/javascript">
  function testJs() {
    alert('Js alert, invoke js function from OC');
    return "alert result NULL";
  }

  var app = {
        callback: function(jsonobj) {
          var tagname = jsonobj.tagname;

          if ( tagname == 'back') {
            History.back();
          }
          else if (tagname == "member_login") {
            alert("手动登录:"+JSON.stringify(jsonobj));
          }
          else if (tagname == "member_register") {
            alert("用户注册:"+JSON.stringify(jsonobj));
          }
        }
    };


  </script>


<ul class="ul1">
   <li class="li2"><a href="ctrip://mainpage?id=132&title=xmxxx">WinPhone link ctrip://mainpage?id=132&title=xmxxx</a></li>
  <br/>
   <li class="li2"><a onclick="javscript:CtripUser.app_member_login()">1. 登录</a></li>
  <br/>
  <li class="li2"><a onclick="javscript:CtripUser.app_member_register()">2. 用户注册</a></li>
  <br/>
  <li class="li2"><a onclick="javscript:CtripUtil.app_cross_package_href('myctrip', 'index.html#common/about?newVer=1')">3. 跨包跳转</a></li>
  <br/>
  <li class="li2"><a onclick="javscript:CtripUtil.app_show_newest_introduction()">4. 新版本欢迎页</a></li>
  <br/> 
   <li class="li2"><a onclick="javscript:CtripUtil.app_open_url('http://www.baidu.com', 2, 'Baidu')">5. 打开Baidu</a></li>
  <br/> 
   <li class="li2"><a onclick="javscript:CtripUtil.app_recommend_app_to_friends()">6. 推荐携程旅行给好友</a></li>
  <br/> 
  <li class="li2"><a onclick="javscript:CtripUtil.app_add_weixin_friend()">7. 添加微信好友</a></li>
  <br/>
  <li class="li2"><a onclick="javascript:CtripUtil.app_call_phone('13800000000')">8. 拨打电话</a></li>
  <br/>
  <li class="li2"><a onclick="javascript:CtripUtil.app_back_to_home()">9. 返回首页</a></li>
  <br/>
  <li class="li2"><a onclick="javascript:CtripUtil.app_back_to_last_page('xxxxxxx')">10. 返回上一页面</a></li>
  <br/>
  <li class="li2"><a onclick="javascript:CtripUtil.app_call_phone('13800138000')">11. 拨打电话</a></li>
  <br/>
  <li class="li2"><a onclick='javascript:CtripUtil.app_call_system_share("http://tongqu.me/upload/photos/acts/normal/norm_2013-12-16-18-56373487fcfe4cb0ecd21c129e1164cc976ab3bf78.jpg", null, "text here")'>12. 调用系统分享_5.3</a>
   </li>
  <br/>
  
  <a onclick="javscript:CtripUtil.app_open_url('http://www.jimzhao.com/qunit/a.html', 2, 'Qunit')">进入自动化测试页面</a>