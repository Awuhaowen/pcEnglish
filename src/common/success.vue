<template>
  <main>
    <div class="mask" v-show="success">
      <div class="con">
        <h2>Submit successfully</h2>
        <p>Submitted successfully. Submitted message sent to your account</p>
        <div>
          <p @click="ck">view invitation List</p>
          <p @click="qt">invite Another Company</p>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  props: {
    success: false
  },

  methods: {
    chaKan() {
      this.$emit("chaKan");
    },

    qiTa() {
      this.$emit("qiTa");
    },

    ck() {
      this.chaKan();
    },

    qt() {
      this.qiTa();
    }
  }
};
</script>

<style scoped>
.con > div > p {
  font-size: 14px;
  background: #007aff;
  color: #fff;
  border-radius: 5px;
  width: 33%;
  text-align: center;
  margin: 10px 400px;
  height: 40px;
  cursor: pointer;
  line-height: 40px;
}

.con > p {
  color: #999;
  line-height: 4;
}

@keyframes go_in {
  0% {
    opacity: 0;
    transform: translateY(50px);
  }
  100% {
    opacity: 1;
  }
}

.con {
  z-index: 999;
  background: #fff;
  width: 600px;
  margin: 30% auto;
  padding: 20px;
  animation: go_in 1s;
}

.mask {
  position: fixed;
  z-index: 999;
  top: 0;
  right: 0;
  overflow: hidden;
  left: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.6);
}
</style>