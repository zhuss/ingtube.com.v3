<template>
  <!--footer-->
  <div class="footer">
    <div class="copy">
      <p>© 2016 映兔科技. All rights reserved</p>
      <p>杭ICP备08104990号</p>
    </div>
  </div>
  <!--footer end-->
</template>
<style scoped>
.footer {
  width: 100%;
  padding: 23px 0;
  background: #242424;
  font-size: 14px;
  line-height: 18px;
  overflow: hidden;
}

.copy {
  width: 100%;
  max-width: 1000px;
  margin: 0 auto;
  overflow: hidden;
}

.footer p {
  width: 50%;
  float: left;
  text-align: left;
  box-sizing: border-box;
  padding-left: 50px;
  color: rgba(255, 255, 255, .3);
}

.footer p:last-child {
  padding-left: 0;
  text-align: right;
  padding-right: 50px;
}

@media screen and (max-width: 750px) {
  .footer p {
    width: 100%;
    text-align: center;
    padding: 0;
  }
  .footer p:last-child {
    text-align: center;
    padding: 0;
  }
}
</style>
