###JS调用Android
```js
//app跳转首页事件

<button  onclick="toIndex();"></button>

function toIndex(){
  //判断手机类型
  var u = navigator.userAgent;
  var isAndroid = u.indexOf('Android') > -1 || u.indexOf('Adr') > -1; //android终端
  var isiOS = !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/); //ios终端

  if(isAndroid){
    window.join.toIndex();//调用Android方法,
  }else if(isiOS){
    toIndex();
  }
}


function cache(){
  var u = navigator.userAgent;
  var isAndroid = u.indexOf('Android') > -1 || u.indexOf('Adr') > -1; //android终端
  var isiOS = !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/); //ios终端

  if(isAndroid){
   // 从app设备获取openId 并设置到浏览器localStorage
    var s = window.join.returnJsOpenId();
    serverApi.setOpenIdToLocalStoreByName('openid',s);
    localStorage.setItem("openID",s);


    //JS获取Android传值并储存到缓存中
    var id = window.join.returnJsOpenId1();
    var protocolName = window.join.returnJsOpenId2();
    var joinNumber = window.join.returnJsOpenId3();
    var latelyNumber = window.join.returnJsOpenId4();
    var minAge = window.join.returnJsOpenId5();
    var maxAge = window.join.returnJsOpenId6();
    //把参数存储到localStorage中；
    localStorage.setItem("planId",id);
    localStorage.setItem('planName',protocolName);
    localStorage.setItem('planJoinNum', joinNumber);
    localStorage.setItem('planLaterNum', latelyNumber);
    localStorage.setItem('planMinAge',minAge);
    localStorage.setItem('planMaxAge',maxAge);
    localStorage.setItem('planEntrance','indexEntrance');
    //少儿  
    $('#childrenJoinNum').html(localStorage.getItem('planJoinNum'));
    $('#childrenJoinThree').html(localStorage.getItem('planLaterNum'));
    //中青年
    $('#youngJoinNum').html(localStorage.getItem('planJoinNum'));
    $('#youngJoinThree').html(localStorage.getItem('planLaterNum'));
    //中老年
    $('#oldJoinNum').html(localStorage.getItem('planJoinNum'));
    $('#oldJoinThree').html(localStorage.getItem('planLaterNum'));
  }else if(isiOS){
  }
}

//Android调用JS方法并传值；
function chuaidi(){
  var u = navigator.userAgent;
  var isAndroid = u.indexOf('Android') > -1 || u.indexOf('Adr') > -1; //android终端
  var isiOS = !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/); //ios终端

  if(isAndroid){
    var a = $('#fillMoney_plan').text();
    var b = $('#fillMoney_name').text();
    var c = $('#fillMoney_card').text();
    var d = $('.money_OrBorder').val();

    window.join.chuangdi(a,b,c,d);
 }
}
```
###JS和OC互相调用
```js
//oc传值，
var ocx = function(openId,id,protocolName,joinNumber,latelyNumber, minAge, maxAge) {
  //获取IOS传来的openID 并设置到浏览器localStorage
  localStorage.setItem("openID",openId);
  var s = openId;
  serverApi.setOpenIdToLocalStoreByName('openid',s);

  //set到缓存中
  localStorage.setItem("planId",id);
  localStorage.setItem('planName',protocolName);
  localStorage.setItem('planJoinNum',joinNumber);
  localStorage.setItem('planLaterNum',latelyNumber);
  localStorage.setItem('planMinAge',minAge);
  localStorage.setItem('planMaxAge',maxAge);
  localStorage.setItem('planEntrance','indexEntrance');
  $('#childrenJoinNum').html(localStorage.getItem('planJoinNum'));
  $('#childrenJoinThree').html(localStorage.getItem('planLaterNum'));
  return;
}
```
