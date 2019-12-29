<template>
  <main style="height: 100vh;background: #fff">
    <el-page-header
      style="padding: 10px; text-aigth: center font-size: 20px;"
      @back="goBack"
      content="information"
    ></el-page-header>

    <div class="xx">
      <h2>@Hello, baidu user</h2>
      <p>
        The meeting you follow has been updated: update content update content
        update content update content update content update content view details
      </p>
      <p style="text-align: right; margin-top: 20upx;">2019-08-12 12:12:50</p>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {};
  },

  methods: {
    goBack() {
      this.$router.push("news");
    }
  }
};
</script>

<style scoped>
.xx {
  padding: 15% 25px 0;
}

.xx > h2 {
  font-size: 24px;
  line-height: 2;
  font-weight: 500;
  color: #666;
}

.xx > p:last-of-type {
  text-align: right;
}

.xx > p {
  color: #959595;
  font-size: 17px;
  line-height: 1.6;
}
</style>
