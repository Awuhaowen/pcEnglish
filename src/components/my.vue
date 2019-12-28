<template>
  <main style="height: 100vh">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">您的位置:</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">首页</p>
      <p style="margin: 0 10px">></p>
      <p>个人中心</p>
    </div>

    <div class="main">
      <div class="hd">
        <div>
          <img src="@/assets/images/huoDong.png" alt="" />
          <p>我的活动</p>
        </div>
        <img src="@/assets/images/youJianTou.png" alt="" />
      </div>

      <div @click="yy" class="hd">
        <div>
          <img src="@/assets/images/yuYue.png" alt="" />
          <p>我的预约</p>
        </div>
        <img src="@/assets/images/youJianTou.png" alt="" />
      </div>

      <div class="wm" v-for="(item, i) in wm" :key="i" @click="gy(i)">
        <div>
          <img :src="item.pic1" alt="" />
          <p>{{ item.p }}</p>
        </div>
        <img :src="item.pic2" alt="" />
      </div>
    </div>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";
export default {
  components: { myHeader },
  data() {
    return {
      wm: [
        {
          pic1: require("@/assets/images/laBa.png"),
          p: "关于我们",
          pic2: require("@/assets/images/youJianTou.png")
        },
        {
          pic1: require("@/assets/images/sheZhi.png"),
          p: "设置",
          pic2: require("@/assets/images/youJianTou.png")
        },
        {
          pic1: require("@/assets/images/tuiChu.png"),
          p: "退出登录",
          pic2: require("@/assets/images/youJianTou.png")
        }
      ]
    };
  },

  methods: {
    sy() {
      this.$router.push("/");
    },

    gy(i) {
      if (i == 0) {
        this.$router.push("About");
      } else if (i == 1) {
        this.$router.push("modify");
      } else {
        this.$router.push('login')
      }
    },

    yy() {
      this.$router.push("yuYue");
    }
  }
};
</script>

<style scoped>
.wm {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #fff;
  cursor: pointer;
  line-height: 50px;
  border-bottom: 1px solid #ececec;
  padding: 0 20px;
}

.wm > div > img {
  margin-right: 10px;
}

.wm > div {
  display: flex;
  align-items: center;
}

.main > .hd > div > img {
  margin-right: 10px;
}

.main > .hd > div {
  display: flex;
  align-items: center;
}

.main > .hd {
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
