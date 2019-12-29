<template>
  <main style="height: 100vh">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">You are here：</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">home</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">personal center</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="setting">setting</p>
      <p style="margin: 0 10px">></p>
      <p>change</p>
    </div>

    <div class="yy">
      <p></p>
      <h4>change password</h4>
    </div>

    <div class="xg">
      <div>
        <p>username：</p>
        <span>tom</span>
      </div>

      <div>
        <p>original password：</p>
        <el-input placeholder="enter your PIN" v-model="input1" show-password></el-input>
      </div>
      <div>
        <p>new code：</p>
        <el-input placeholder="Please enter the originali password" v-model="input2" show-password></el-input>
      </div>
      <div>
        <p>confirm password：</p>
        <el-input
          placeholder="Please enter your confirmation password"
          v-model="input3"
          show-password
        ></el-input>
      </div>
      <div class="tj">
        <el-button class="cg" :plain="true" @click="open2">submit</el-button>
      </div>
    </div>
    <div id="btn">
      <p @click="gr">return</p>
    </div>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";

export default {
  components: { myHeader },
  data() {
    return {
      input1: "",
      input2: "",
      input3: ""
    };
  },

  methods: {
    sy() {
      this.$router.push("/");
    },

    setting() {
      this.$router.push("modify");
    },

    open2() {
      this.$message({
        message: "提交成功",
        type: "success"
      });
    },

    gr() {
      this.$router.push("my");
    }
  }
};
</script>

<style scoped>
#btn {
  text-align: center;
  width: 70%;
  cursor: pointer;
  margin: 20px auto;
}

#btn > p {
  line-height: 40px;
  color: #fff;
  background-color: #007aff;
  border-radius: 5px;
  text-align: center;
}

.xg > .tj {
  height: 70px;
  border-bottom: 2px dashed #bbbbbb;
}

.cg {
  color: #007aff;
  border: 1px dashed #007aff;
  text-align: center;
  width: 187px;
  font-weight: 400;
  font-size: 16px;
  line-height: 17px;
  cursor: pointer;
  border-radius: 5px;
  margin: 25px auto;
}

.xg > div > p {
  width: 110px;
}

.xg {
  background: #fff;
  padding: 10px;
}

.xg > div {
  display: flex;
  align-items: center;
  margin: 10px 0;
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

.yy {
  display: flex;
  align-items: center;
  background: #fff;
  padding: 10px;
  margin-top: 10px;
}

.yy > p {
  width: 5px;
  height: 20px;
  margin-right: 5px;
  background-color: #007aff;
}
</style>
