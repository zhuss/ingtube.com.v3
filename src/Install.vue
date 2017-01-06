<template>
  <div id="app">
    <p>正在下载...</p>
  </div>
</template>
<script>
var inWX = navigator.userAgent.toLowerCase().indexOf('micromessenger') != -1;
var isIPhone = navigator.userAgent.toLowerCase().indexOf('iphone') != -1;

if (inWX) {
  location.href = "http://a.app.qq.com/o/simple.jsp?pkgname=com.ingtube.yingtu";
} else {
  if (isIPhone) {
    //ios应用
    location.href = "https://itunes.apple.com/cn/app/ying-tu/id1118660214";
  } else {
    //安卓apk包
    location.href = "http://pv.yingtu.co/android/yingtu.apk";
  }
}
</script>
