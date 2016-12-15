# 瀑布流插件插件demo，初学者可以拿来练手


- 使用(基于jquery，必须先引入jquery)
```shell
  <link rel="stylesheet" href="css/reset.css" />  <!-- 初始化浏览器默认样式 -->
  <link rel="stylesheet" type="text/css" href="css/style.css"/>
  <script src="js/jquery-1.10.min.js"></script>
  <script src="js/jquery.falless.js"></script>
```
- html结构
```shell
  <div id="container" class="clearfix">
    <div class="gird img-box-x">
      <div class="nr shadow">
        <img src="images/1.jpg" alt="">
      </div>
    </div>
  </div> 
```
- 插件调用
```shell
window.onload=function(){
  $("#container").falless({
  offsetY:15,
  //、、、
})
```
- 如果需要下拉加载需要自己添加下拉加载功能（这里给个模拟示例）
```shell
window.onload=function(){
  $("#container").falless({offsetY:15,})
    window.onscroll=function(){
      winH=$(window).height();
      docH=$("body").height();
      scrTop=$(window).scrollTop();
      if((scrTop+winH+100)>=docH){
        var a;
        for (var i = 1; i <7; i++) {
          if(i%2==0){
            a=1
          }else{
            a=2
          }
          var gird=$('<div class="gird img-box-x">');
          var nr=$('<div class="nr shadow">');
          var img=$('<img src="images/'+a+'.jpg" alt="">');
          $("#container").append(gird.append(nr.append(img)))
        };
        $("#container").falless({offsetY:15,})
      }
    }
}
```
- 演示地址
  https://hellosanbao.github.io/git-falless/