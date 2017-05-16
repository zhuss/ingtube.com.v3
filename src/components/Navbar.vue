<template>
  <!--nav-->
  <div class="nav">
    <ul>
      <li><a :class="active=='index'?'active':''" href="index.html">首页</a></li>
      <li><a :class="active=='about'?'active':''" href="about.html">关于</a></li>
      <li><a href="javascript:;" @click="dialog = true">入驻</a></li>
    </ul>
    <div class="dialog" v-if="dialog" @click.self="dialog = false">
      <h2>入驻映兔视频</h2>
      <div class="dialog-content">
        <p>请下载入驻申请表，填写后发送至leyao@ingtube.com，我们会在第一时间回复。</p>
        <p>表格下载地址：<a href="http://cdn.bunny-tech.com/promotion/static/res/%E6%98%A0%E5%85%94%E8%A7%86%E9%A2%91%E6%B3%A8%E5%86%8C.xlsx">映兔视频注册.xlsx</a></p>
        <p style="text-align:center; padding-top: 50px;">
          <button @click="dialog = false">知道了</button>
        </p>
      </div>
    </div>
  </div>
  <!--nav end-->
</template>
<script>
export default {
  props: {
    active: {
      type: String,
      default: 'index'
    }
  },
  data() {
    return {
      dialog: false
    }

  }
}
</script>
<style scoped>
.nav {
  position: absolute;
  top: 32px;
  right: 220px;
  text-align: center;
}

.nav ul {
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

.nav ul li {
  padding: 0 30px;
}

.dialog {
  position: fixed;
  top: 0;
  left: 0;
  background: rgba(0, 0, 0, .9);
  z-index: 1000;
  width: 100%;
  height: 100%;
  color: #FFF;
}

.dialog h2 {
  font-size: 18px;
  font-weight: normal;
  height: 100px;
  line-height: 100px;
}

.dialog-content {
  width: 400px;
  text-align: left;
  margin: 0 auto;
}

.dialog-content p {
  padding: 10px 0;
}

.dialog-content p a {
  color: #F8CA03;
}

.dialog-content button {
  background: #F8CA03;
  border: none;
  width: 100px;
  height: 30px;
  border-radius: 30px;
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
    display: inline-block;
    margin: 0 auto;
  }
  .dialog-content {
    width: 300px;
    text-align: left;
    margin: 0 auto;
  }
}
</style>
