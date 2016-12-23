<template>
  <!--nav-->
  <div class="nav">
    <ul>
      <li><a :class="active=='index'?'active':''" href="index.html">首页</a></li>
      <li><a :class="active=='about'?'active':''" href="about.html">关于</a></li>
    </ul>
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
  }
}
</script>
<style scoped>
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
}
</style>
