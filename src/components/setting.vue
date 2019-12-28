<template>
  <main style="height: 100vh">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">您的位置:</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">首页</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">个人中心</p>
      <p style="margin: 0 10px">></p>
      <p>修改密码</p>
    </div>

    <div class="yy">
      <p></p>
      <h4>修改密码</h4>
    </div>

    <div class="xg">
      <div>
        <p>用户名：</p>
        <span>tom</span>
      </div>

      <div>
        <p>原密码：</p>
        <el-input
          placeholder="请输入原密码"
          v-model="input1"
          show-password
        ></el-input>
      </div>
      <div>
        <p>新密码：</p>
        <el-input
          placeholder="请输入新密码"
          v-model="input2"
          show-password
        ></el-input>
      </div>
      <div>
        <p>确认密码：</p>
        <el-input
          placeholder="请确认密码"
          v-model="input3"
          show-password
        ></el-input>
      </div>
      <div class="tj">
        <el-button class="cg" :plain="true" @click="open2">提交</el-button>
      </div>
      <h4 @click="gr" class="fh">返回</h4>
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
.fh {
  color: #fff;
  background-color: #007aff;
  width: 90%;
  height: 40px;
  line-height: 40px;
  margin: 225px auto 10px;
  text-align: center;
  border-radius: 5px;
  cursor: pointer;
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
