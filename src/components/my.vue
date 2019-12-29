<template>
  <main style="height: 100vh">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">You are here：</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">home</p>
      <p style="margin: 0 10px">></p>
      <p>personal center</p>
    </div>

    <div class="main">
      <div class="wm" v-for="(item, i) in wm" :key="i" @click="gy(i)">
        <div>
          <img :src="item.pic1" alt />
          <p>{{ item.p }}</p>
        </div>
        <img :src="item.pic2" alt />
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
          pic1: require("@/assets/images/yuYue.png"),
          p: "My Bookings",
          pic2: require("@/assets/images/youJianTou.png")
        },
        {
          pic1: require("@/assets/images/laBa.png"),
          p: "About Us",
          pic2: require("@/assets/images/youJianTou.png")
        },
        {
          pic1: require("@/assets/images/sheZhi.png"),
          p: "Setting",
          pic2: require("@/assets/images/youJianTou.png")
        },
        {
          pic1: require("@/assets/images/tuiChu.png"),
          p: "Log off",
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
      if (i == 1) {
        this.$router.push("About");
      } else if (i == 2) {
        this.$router.push("modify");
      } else if (i == 3) {
        this.$router.push("login");
      } else if (i == 0) {
        this.$router.push("yuYue");
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
  margin: 20px 0;
  line-height: 51px;
  box-shadow: 1px 1px 2px #dcdcdc;
  border-left: 2px solid #007aff;
}
</style>
