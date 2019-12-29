<template>
  <main style="height: 100vh">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">You are here：</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">home</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">personal center</p>
      <p style="margin: 0 10px">></p>
      <p>setting</p>
    </div>

    <div @click="yy" class="hd">
      <div>
        <img src="@/assets/images/yuYue.png" alt />
        <p>Change Password</p>
      </div>
      <img src="@/assets/images/youJianTou.png" alt />
    </div>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";

export default {
  components: { myHeader },
  data() {
    return {};
  },

  methods: {
    sy() {
      this.$router.push("/");
    },

    yy() {
      this.$router.push("setting");
    },

    gr() {
      this.$router.push("my");
    }
  }
};
</script>

<style scoped>
.hd > div > p {
  font-size: 14px;
  color: #999;
}

.hd > div > img {
  margin-right: 10px;
}

.hd > div {
  display: flex;
  align-items: center;
}

.hd {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #fff;
  cursor: pointer;
  margin: 15px 0;
  line-height: 50px;
  padding: 0 20px;
}

.head > p {
  color: #999;
  font-size: 12px;
}

.head {
  overflow: hidden;
  background-color: #ffffff;
  display: flex;
  align-items: center;
  border-radius: 4px;
  line-height: 40px;
  box-shadow: 1px 1px 2px #dcdcdc;
  border-left: 2px solid #007aff;
}
</style>
