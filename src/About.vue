<template>
  <div id="app">
    <div class="top">
      <div class="bg">
        <img src="./assets/img/bg.jpg" />
      </div>
      <!--nav-->
      <div class="nav">
        <ul>
          <li><a href="index.html">首页</a></li>
          <li><a class="active" href="#">关于</a></li>
        </ul>
      </div>
      <!--nav end-->
      <!--icon-->
      <div class="icon">
        <img src="./assets/img/icon.png" />
      </div>
      <!--icon end-->
      <!--info-->
      <div class="info">
        <h2>看看是谁创造了映小兔</h2>
        <p>映兔是一个强调开放和信任、追求效率和极致的创业团队。在这里，有吃不完的零食饮料和玩不完的团队建设；在这里，我们享受技术与设计的相爱相杀，上一秒产品开发撕B大战，下一秒挡拆配合打爆全场；当然，在这里还有一份充满竞争力的薪资以及让你实现梦想的股权激励计划。</p>
        <a class="btn" href="javascript:;" @click="isShowModel = true">加入我们</a>
      </div>
      <!--info end-->
      <!--pic-->
      <div class="pic">
        <div class="pic-box">
          <img src="./assets/img/pic1.png" />
          <img src="./assets/img/pic2.png" />
          <img src="./assets/img/pic3.png" />
          <img src="./assets/img/pic4.png" />
        </div>
      </div>
      <!--pic end-->
    </div>
    <!--main-->
    <div class="main">
      <div class="concat-bg"></div>
      <div class="concat">
        <h2>咖啡供应</br>欢迎来映兔坐坐</h2>
        <p>杭州市西湖区崇义路郡原公元里13幢3楼</p>
        <p>0571-83489234</p>
        <p>business@ingtube.com</p>
        <p>support@ingtube.com</p>
      </div>
    </div>
    <!--main end-->
    <!--footer-->
    <div class="footer">
      <p>© 2016 映兔科技. All rights reserved</p>
      <p>杭ICP备08104990号</p>
    </div>
    <!--footer end-->
    <!--model-->
    <transition name="fade">
      <div class="model" v-show="isShowModel">
        <div class="mark" @click="isShowModel = false"></div>
        <div class="model-content">
          <span class="close" @click="isShowModel = false"><img src="./assets/img/close.png"/></span>
          <ul>
            <li @click="index =1" :class="index == 1? 'active':''">技术</li>
            <li @click="index =2" :class="index == 2? 'active':''">产品设计</li>
            <li @click="index =3" :class="index == 3? 'active':''">运营</li>
          </ul>
          <div class="teaminfo" v-show="index ==1">
            <p>我们不是普通意义的技术团队。</p>
            <p>我们以 Google 的技术标准要求自己，鼓励使用新技术、鼓励重新造轮子、鼓励全栈。</p>
            <p>我们实行 OKR 制度，强调自我驱动和扁平管理。</p>
            <p>我们的工作领域：</p>
            <p>· 机器学习：深度学习在图像、语音、NLP上的应用VR/AR 技术</p>
            <p>· 后端技术：包括微服务、kubernetes、DevOps、CI/CD、搜索推荐、即时通讯、数据监控和报警</p>
            <p>· 前端技术：iOS、Android、H5 的新技术</p>
            <p>· 音视频技术：编解码、传输和直播技术</p>
            <p>搜索 “映兔技术团队” 关注我们的微信公众号。</p>
          </div>
          <div class="teaminfo" v-show="index ==2">
            <p>我们来自阿里巴巴、腾讯、网易等公司，专注于服务商业的产品、交互与视觉设计，目标是创造出移动营销时代的优秀产品。视频与直播、本地生活、社交、AR&VR都是我们的研究领域，如果你也对以上领域感兴趣，欢迎加入。</p>
          </div>
          <div class="teaminfo" v-show="index ==3">
            <p>拳怕少壮，我们是一群来自各大互联网公司一线运营岗位的年轻90后团队。专注于服务b端商家和c端用户，营造更舒适的体验和更精准的营销！团队塑造简单工作，高效运作的理念，力争在谈笑间开疆拓土。如果你也是一个厌倦了戴上枷锁跳舞的工作方式，向往自由free的工作氛围，欢迎加入我们。 </p>
            <p>成功的路上你需要99%的努力，而我们则是剩下的那1%机遇。</p>
          </div>
          <div class="email">
            hr@ingtube.com
          </div>
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
      isShowModel: false,
      index: 1
    }
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

#app {
  height: 100%;
}

.top {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.bg {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.bg img {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
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

.info {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 504px;
  margin-top: -50px;
}

.info h2 {
  text-align: center;
  font-size: 40px;
  line-height: 52px;
  font-weight: 100;
  color: #FFF;
  margin-bottom: 28px;
}

.info p {
  width: 100%;
  text-align: center;
  color: #FFF;
  font-size: 14px;
  line-height: 22px;
  margin-bottom: 98px;
}

.info .btn {
  display: block;
  color: #000;
  width: 172px;
  height: 48px;
  background: #F8CA03;
  font-size: 18px;
  text-align: center;
  line-height: 48px;
  border-radius: 48px;
  margin: 0 auto;
}

.pic {
  left: 50%;
  transform: translateX(-50%);
  width: 784px;
  position: absolute;
  bottom: 46px;
}

.pic-box {
  width: 784px;
  height: 110px;
  overflow: hidden;
}

.pic-box img {
  display: block;
  width: 180px;
  height: 110px;
  float: left;
  margin: 0 8px;
}

.main {
  position: relative;
  overflow: hidden;
}

.concat-bg {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 396px;
  height: 396px;
  border: 20px solid rgba(255, 255, 255, .3);
  background: rgba(248, 202, 3, .6);
  border-radius: 50%;
  margin-top: -50px;
  z-index: -1;
}

.concat {
  text-align: center;
  padding: 71px 0 79px;
}

.concat h2 {
  font-size: 22px;
  line-height: 28px;
  margin-bottom: 28px;
}

.concat p {
  font-size: 14px;
  line-height: 20px;
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
  padding: 28px 130px 36px 40px;
}

.model-content .close {
  position: absolute;
  right: 24px;
  top: 24px;
  width: 16px;
  height: 16px;
}

.model-content .close img {
  display: block;
  width: 100%;
}

.model-content ul {
  overflow: hidden;
  margin-bottom: 28px;
}

.model-content ul li {
  float: left;
  margin-right: 28px;
  font-size: 18px;
  line-height: 25px;
  padding-bottom: 5px;
  color: #AEAEAE;
  border-bottom: 3px solid #FFF;
  cursor: pointer;
}

.model-content ul li.active {
  border-bottom: 3px solid #F8CA03;
  color: #000;
}

.model-content .teaminfo {
  color: #AEAEAE;
  font-size: 12px;
  line-height: 17px;
  width: 350px;
  height: 217px;
  overflow: hidden;
}

.model-content .email {
  font-size: 14px;
  line-height: 20px;
}

@media screen and (max-width: 750px) {
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
    display: none;
  }
  .info {
    width: 284px;
  }
  .info h2 {
    width: 180px;
    margin-left: auto;
    margin-right: auto;
    font-size: 28px;
    line-height: 37px;
    font-weight: bolder;
    margin-bottom: 18px;
  }
  .info p {
    margin-bottom: 30px;
  }
  ::-webkit-scrollbar {
    display: none;
  }
  .pic {
    -webkit-overflow-scrolling: touch;
    width: 100%;
    bottom: 30px;
    overflow-x: scroll;
  }
  .concat-bg {
    display: none;
  }
  .concat {
    padding: 79px 0 100px;
  }
  .footer p {
    width: 100%;
  }
  .model .model-content {
    width: 280px;
    padding-left: 10px;
    padding-right: 10px;
  }
  .model-content .teaminfo {
    width: 100%;
  }
  .model-content .email {
    padding-top: 10px;
  }
}
</style>
