<template>
  <div id="app">
    <div class="top">
      <div class="video">
        <video autoplay="autoplay" loop="true" :src="videoUrl" webkit-playsinline="false" playsinline="false">
        </video>
      </div>
      <div class="bg-ms">
        <transition name="tran" v-for="(item,index) in imgUrls">
          <img v-show="imgIndex==index" :src="item" />
        </transition>
      </div>
      <!--nav-->
      <div class="nav">
        <ul>
          <li><a class="active" href="#">首页</a></li>
          <li><a href="about.html">关于</a></li>
        </ul>
      </div>
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
    <div class="footer">
      <p>© 2016 映兔科技. All rights reserved</p>
      <p>杭ICP备08104990号</p>
    </div>
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

export default {
  data() {
      return {
        isShowQrcode: false,
        imgIndex: 0,
        videoUrl: "http://static.kaiyanapp.com/eyepetizer-web/homepage.mp4",
        imgUrls: ["http://static.kaiyanapp.com/eyepetizer-web/assets/images/index/home_bk_7.8b2d29b4.jpg", "http://static.kaiyanapp.com/eyepetizer-web/assets/images/index/home_bk_5.c48e7769.jpg"]
      }
    },
    mounted() {
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
  -webkit-transition: all .5s;
  transition: all .5s;
}

.fade-enter,
.fade-leave-active {
  opacity: 0;
  transform: scale(1.2);
}


/*图片显示动画*/

.tran-enter-active,
.tran-leave-active {
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
}

.video video {
  left: 50%;
  min-height: 100%;
  min-width: 100%;
  position: absolute;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
}

.bg-ms {
  position: absolute;
  width: 100%;
  height: 100%;
  display: none;
}

.nav {
  width: 130px;
  position: absolute;
  top: 32px;
  right: 220px;
}

.nav ul {
  width: 130px;
  height: 24px;
  line-height: 24px;
}

.nav ul li {
  float: left;
}

.nav a {
  color: rgba(255, 255, 255, .3);
}

.nav a.active {
  color: rgba(255, 255, 255, 1);
}

.nav ul li:first-child {
  margin-right: 74px;
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
  width: 80%;
  height: auto;
  overflow: hidden;
  margin: 0 auto;
  padding-bottom: 60px;
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

.footer {
  width: 100%;
  padding: 23px 0;
  background: #242424;
  color: rgba(255, 255, 255, .5);
  font-size: 14px;
  line-height: 18px;
  overflow: hidden;
  font-weight: 100;
}

.footer p {
  width: 50%;
  float: left;
  text-align: center;
  font-weight: 100;
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

@media screen and (max-width: 750px) {
  .video {
    display: none;
  }
  .bg-ms {
    position: absolute;
    display: block;
    animation: scale 10s ease-in-out infinite;
    z-index: -1;
  }
  @keyframes scale {
    from {
      transform: scale(1);
    }
    to {
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
  .nav {
    width: 100%;
    height: 24px;
    padding: 13px 0;
    background: rgba(0, 0, 0, .2);
    top: 0;
    right: 0;
  }
  .nav ul {
    margin: 0 auto;
  }
  .icon {
    width: 87px;
    height: 87px;
    top: 20%;
    left: 50%;
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
  .footer p {
    width: 100%;
  }
}
</style>
