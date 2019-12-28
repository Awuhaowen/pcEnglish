<template>
  <main>
    <div class="head">
      <img src="@/assets/images/logo.png" alt="" />
      <div>
        <img src="@/assets/images/yongHu.png" @click="yh" alt="" />
        <div class="hongDian"></div>
        <img src="@/assets/images/youXiang.png" @click="xx" alt="" />
      </div>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {};
  },

  methods: {
    yh() {
      this.$router.push("my");
    },

    xx() {
      this.$router.push("news");
    }
  }
};
</script>

<style scoped>
.head > div > img {
  width: 25px;
}

main {
  background: #fff;
}

.hongDian {
  width: 8px;
  height: 8px;
  text-align: center;
  position: absolute;
  top: 0px;
  border-radius: 100%;
  right: -2px;
  z-index: 999;
  line-height: 40px;
  background-color: rgb(255, 2, 2);
}

.head > div {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 12%;
  cursor: pointer;
  position: relative;
}

.head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
}

.head > img {
  width: 40%;
  height: 45px;
}
</style>
