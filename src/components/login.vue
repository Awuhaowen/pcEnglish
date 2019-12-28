<template>
  <main style="height: 100vh">
    <div class="con">
      <img src="@/assets/images/logo.png" alt="" />

      <div class="dl">
        <div class="d">
          <p>手机号登录</p>
          <p>邮箱登录</p>
        </div>

        <div class="p">
          <p>手机号:</p>
          <el-input v-model="input1" placeholder="请输入手机号"></el-input>
        </div>

        <div class="p">
          <p>验证码:</p>
          <el-input v-model="input2" placeholder="请输入验证码"></el-input>
          <span>点击获取</span>
        </div>
        <p @click="dl" class="fh">登录</p>
      </div>
    </div>
    <p>© 中国机电产品进出口商会</p>
  </main>
</template>

<script>
export default {
  data() {
    return {
      input1: "",
      input2: ""
    };
  },

  methods: {
    dl() {
      this.$router.push("/");
    }
  }
};
</script>

<style scoped>
main > p {
  text-align: center;
  margin-top: 25%;
}

.fh {
  color: #fff;
  background-color: #007aff;
  width: 90%;
  height: 40px;
  line-height: 40px;
  margin: 70px auto 10px;
  text-align: center;
  border-radius: 5px;
  cursor: pointer;
}

.dl > .p > span {
  position: absolute;
  top: 174px;
  right: 40px;
  color: #007aff;
  cursor: pointer;
}

.dl > .p > p {
  line-height: 40px;
  position: relative;
}

.dl > .d {
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.con > .dl {
  padding: 25px;
  background: #fff;
  margin-top: 40px;
  box-shadow: rgba(0, 0, 0, 0.16) 1px 1px 1px 0px;
  border-radius: 2px;
  font-size: 14px;
  position: relative;
  width: 70%;
  margin: auto;
}

.con {
  width: 80%;
  margin: auto;
}

.con > img {
  width: 70%;
  height: 70px;
  display: block;
  margin: auto;
  padding: 80px;
}
</style>
