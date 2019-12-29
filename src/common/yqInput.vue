<template>
  <main>
    <div class="mask" v-show="tc">
      <div class="con">
        <h1>invitation</h1>
        <p>
          Please leave your information and choose the time if you want to have
          a B2B meeting with our company.
        </p>

        <div>
          <p>
            <span>*</span>Your Company Name:
          </p>
          <el-input v-model="input1" placeholder="default  your Company Name"></el-input>
        </div>
        <div>
          <p>
            <span>*</span>Your Time Selection：
          </p>
          <select
            style="width: 100%;
                border: 1px solid #C0C4CC;
                outline: none;
                border-radius: 4px;
                height: 40px;
                color: #606266;"
          >
            <option value>15:00-15:15</option>
            <option value>15:30-15:45</option>
          </select>
        </div>
        <div>
          <p>
            <span>*</span>Your Name:
          </p>
          <el-input v-model="input2" placeholder="default enter your  Name"></el-input>
        </div>
        <div>
          <p>Your Telephone No:</p>
          <el-input v-model="input3" placeholder="default enter  Your  Telephone "></el-input>
        </div>
        <div>
          <p>
            <span>*</span>Your Emal Address:
          </p>
          <el-input v-model="input4" placeholder="default enter your Emal"></el-input>
        </div>
        <div>
          <p>Your interflow:</p>
          <el-input
            type="textarea"
            :autosize="{ minRows: 3, maxRows: 5}"
            placeholder="Please enter your  MESSAGE"
            v-model="textarea2"
          ></el-input>
        </div>

        <div id="btn">
          <p @click="tiJiao">Submission</p>
          <p @click="fanHui">Ruturn</p>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  props: {
    tc: false
  },

  data() {
    return {
      input1: "",
      input2: "",
      input3: "",
      input4: "",
      textarea2: ""
    };
  },

  methods: {
    tj() {
      this.$emit("tj");
    },
    
    fh() {
      this.$emit("fh");
    },

    tiJiao() {
      this.tj();
    },

    fanHui() {
      this.fh();
    }
  }
};
</script>

<style scoped>
.con > #btn > p {
  padding: 5px 10px;
  border: 1px dashed #007aff;
  font-size: 12px;
  width: 80px;
  text-align: center;
  line-height: 25px;
  border-radius: 5px;
  color: #007aff;
  cursor: pointer;
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

.con > #btn {
  display: flex;
  align-items: center;
  margin-top: 30px;
  justify-content: space-around;
}

.con > div > p {
  line-height: 3;
}

.con > p {
  color: #999;
  margin: 10px 0;
}

.con > h1 {
  text-align: center;
  border-bottom: 1px dashed #007aff;
  width: 30%;
  margin: auto;
}

.con {
  z-index: 999;
  background: #fff;
  width: 600px;
  margin: 5% auto;
  padding: 10px;
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