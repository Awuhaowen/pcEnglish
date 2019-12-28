<template>
  <main style="height: 100vh">
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt="" />
    <div class="btn">
      <p v-for="(item, i) in btn" :key="i" @click="b(i)">{{ item }}</p>
    </div>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";
export default {
  components: { myHeader },
  data() {
    return {
      btn: ["活动介绍", "论坛报名", "签约项目申报", "展示项目申报", "活动主题"]
    };
  },
  methods: {
    b(i) {
      if (i == 0) {
        this.$router.push("activity");
      } else if (i == 4) {
        this.$router.push("zhuTi");
      }
    }
  }
};
</script>

<style scoped>
.btn > p {
  border: 1px solid #007aff;
  width: 80%;
  text-align: center;
  border-radius: 5px;
  cursor: pointer;
  margin: 20px auto;
  color: #007aff;
  padding: 13px 0;
}

main {
  background: #fff;
}
</style>
