<template>
  <div id="app">
    <!--top-->
    <div class="top">
      <!--pc端video-->
      <div class="video">
        <video id="video" autoplay="autoplay" loop="true" :src="videoUrl" webkit-playsinline="false" playsinline="false">
        </video>
      </div>
      <!--pc端video end-->
      <!--mobile端 图片-->
      <div class="bg-ms">
        <transition name="tran" v-for="(item,index) in imgUrls">
          <img v-show="imgIndex==index" :src="item" />
        </transition>
      </div>
      <!--mobile端 图片-->
      <!--nav-->
      <navbar></navbar>
      <!--nav end-->
      <!--icon-->
      <div class="icon">
        <img src="./assets/img/icon.png" />
      </div>
      <!--icon end-->
      <!--logo-->
      <div class="logo">
        <!--btn-->
        <div class="btn-down">
          <a class="btn-pc" href="javascript:;" @click="isShowQrcode = true">下载客户端</a>
          <a class="btn-ms" href="#">下载客户端</a>
        </div>
        <!--btn end-->
      </div>
      <!--logo-->
    </div>
    <!--topend-->
    <!--main-->
    <div class="main">
      <div class="card">
        <img src="./assets/img/icon-topic.png" />
        <h2>发现主题</h2>
        <p>发现精彩主题</br>聚合全网海量视频</p>
      </div>
      <div class="card">
        <img src="./assets/img/icon-tu.png" />
        <h2>兔子洞</h2>
        <p>每天更新你喜欢</br>的精彩视频</p>
      </div>
      <div class="card">
        <img src="./assets/img/icon-push.png" />
        <h2>即时推送</h2>
        <p>开启即时推送</br>不错过任何新视频</p>
      </div>
      <div class="card">
        <img src="./assets/img/icon-tv.png" />
        <h2>映兔TV</h2>
        <p>懒人必备</br>你的专属移动电视</p>
      </div>
    </div>
    <!--main-->
    <!--footer-->
    <bottom></bottom>
    <!--footer end-->
    <!--model-->
    <transition name="fade">
      <div class="model" v-show="isShowQrcode">
        <div class="mark" @click="isShowQrcode = false"></div>
        <div class="model-content">
          <h2>扫描二维码下载</h2>
          <p>也可以在AppStore、各大安</br>卓市场搜索“映兔视频”</p>
          <img src="./assets/img/QRcode.png" />
        </div>
      </div>
    </transition>
    <!--model end-->
  </div>
</template>
<script>
require('assets/css/common.css')

import Bottom from './components/Bottom'
import Navbar from './components/Navbar'


export default {
  components: {
    Bottom,
    Navbar
  },
  data() {
    return {
      isShowQrcode: false,
      imgIndex: 0,
      videoUrl: "http://pv.yingtu.co/video/b498f429-2c31-4a7e-b49f-409bafbc6408.mp4",
      //"http://cdn.bunny-tech.com/promotion/static/act-videos/ingtube.mp4",  
      imgUrls: [
        "http://static.kaiyanapp.com/eyepetizer-web/assets/images/index/home_bk_7.8b2d29b4.jpg",
        "http://static.kaiyanapp.com/eyepetizer-web/assets/images/index/home_bk_5.c48e7769.jpg"
      ]
    }
  },
  mounted() {
    //设置静音
    document.getElementById("video").muted = true;
    var self = this;
    setInterval(function() {
      if (self.imgIndex < self.imgUrls.length - 1) {
        self.imgIndex++;
      } else {
        self.imgIndex = 0;
      }
    }, 10000)
  }
}
</script>
<style>
.fade-enter-active,
.fade-leave-active {
  -ms-transition: all .5s;
  -moz-transition: all .5s;
  -o-transition: all .5s;
  -webkit-transition: all .5s;
  transition: all .5s;
}

.fade-enter,
.fade-leave-active {
  opacity: 0;
  -ms-transform: scale(1.2);
  -moz-transform: scale(1.2);
  -o-transform: scale(1.2);
  -webkit-transform: scale(1.2);
  transform: scale(1.2);
}


/*图片显示动画*/

.tran-enter-active,
.tran-leave-active {
  -ms-transition: opacity .5s;
  -moz-transition: opacity .5s;
  -o-transition: opacity .5s;
  -webkit-transition: opacity .5s;
  transition: opacity .5s;
}

.tran-enter,
.tran-leave-active {
  opacity: 0;
}

#app {
  height: 100%;
}

.top {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.video {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: -1;
  display: block;
  background: #000;
}

.video video {
  left: 50%;
  min-height: 100%;
  min-width: 100%;
  position: absolute;
  -ms-transform: translateX(-50%);
  -moz-transform: translateX(-50%);
  -o-transform: translateX(-50%);
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
}

.bg-ms {
  position: absolute;
  width: 100%;
  height: 100%;
  display: none;
}

.icon {
  position: absolute;
  left: 220px;
  top: 27px;
  width: 32px;
  height: 32px;
}

.icon img {
  display: block;
  width: 100%;
}

.logo {
  position: relative;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  -moz-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  width: 172px;
  padding-top: 328px;
  background: url('http://cdn.bunny-tech.com/promotion/static/act-imags/logo-pc.31a2d59.png') no-repeat center top;
  background-size: 124px;
}

.btn-down {
  width: 172px;
  height: 48px;
}

.btn-pc,
.btn-ms {
  display: block;
  width: 172px;
  height: 48px;
  background: #F8CA03;
  color: #000;
  text-align: center;
  line-height: 48px;
  border-radius: 48px;
  font-size: 18px;
  font-weight: 500;
}

.btn-ms {
  display: none;
}

.main {
  width: 1000px;
  height: auto;
  overflow: hidden;
  margin: 0 auto;
  padding-bottom: 60px;
  background: #FFF;
}

.main .card {
  width: 25%;
  float: left;
  margin-top: 60px;
}

.card img {
  display: block;
  width: 72px;
  height: 72px;
  margin: 0 auto;
  margin-bottom: 32px;
}

.card h2 {
  font-size: 22px;
  font-weight: 500;
  text-align: center;
  margin-bottom: 11px;
}

.card p {
  text-align: center;
  font-size: 14px;
  color: #7D7D7D;
  line-height: 18px;
}

.model {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 100;
}

.model .mark {
  position: absolute;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, .5);
}

.model .model-content {
  position: absolute;
  left: 50%;
  top: 50%;
  -ms-transform: translate(-50%, -50%);
  -moz-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  background: #FFF;
  width: 260px;
  height: 320px;
  border-top: 5px solid #F8CA03;
  text-align: center;
}

.model-content h2 {
  padding-top: 32px;
  padding-bottom: 4px;
  font-size: 18px;
}

.model-content p {
  font-size: 12px;
  line-height: 17px;
  color: #AEAEAE;
}

.model-content img {
  width: 152px;
  height: 152px;
  margin-top: 30px;
}

@media screen and (max-width: 1000px) {
  .main {
    width: 100%;
  }
}

@media screen and (max-width: 750px) {
  .video {
    display: none;
  }
  .bg-ms {
    position: absolute;
    display: block;
    -ms-animation: scale 10s ease-in-out infinite;
    -moz-animation: scale 10s ease-in-out infinite;
    -o-animation: scale 10s ease-in-out infinite;
    -webkit-animation: scale 10s ease-in-out infinite;
    animation: scale 10s ease-in-out infinite;
    z-index: -1;
  }
  @keyframes scale {
    from {
      -ms-transform: scale(1);
      -moz-transform: scale(1);
      -o-transform: scale(1);
      -webkit-transform: scale(1);
      transform: scale(1);
    }
    to {
      -ms-transform: scale(1.2);
      -moz-transform: scale(1.2);
      -o-transform: scale(1.2);
      -webkit-transform: scale(1.2);
      transform: scale(1.2);
    }
  }
  .bg-ms img {
    position: absolute;
    top: 0;
    left: 0;
    display: block;
    min-width: 100%;
    min-height: 100%;
  }
  .icon {
    width: 87px;
    height: 87px;
    top: 20%;
    left: 50%;
    -ms-transform: translateX(-50%);
    -moz-transform: translateX(-50%);
    -o-transform: translateX(-50%);
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
  }
  .logo {
    top: 60%;
    padding-top: 178px;
    background: url('http://cdn.bunny-tech.com/promotion/static/act-imags/logo-ms.5decc99.png') no-repeat center top;
    background-size: 150px;
  }
  .btn-pc {
    display: none;
  }
  .btn-ms {
    display: block;
  }
  .main {
    width: 100%;
  }
  .main .card {
    width: 50%;
  }
}
</style>
