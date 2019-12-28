<template>
  <main style="height: 100vh;background: #fff">
    <el-page-header
      style="padding: 10px; text-aigth: center"
      @back="goBack"
      content="消息"
    >
    </el-page-header>

    <div class="xx">
      <h2>@Artepharm Co., Ltd., China您好。</h2>
      <p>
        你关注的
        <span style="color: #007aff">第二届中日第三方市场合作论坛</span>
        有更新：您的邀约已通过，感谢您的参加。
      </p>
      <p style="margin-top: 20px;">2019-11-15 12:12:50</p>
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
  font-size: 18px;
  color: #101010;
  font-weight: 500;
  line-height: 3;
}

.xx > p:last-of-type {
  text-align: right;
}

.xx > p {
  font-size: 14px;
  color: #5e5e5e;
  line-height: 25px;
}
</style>
