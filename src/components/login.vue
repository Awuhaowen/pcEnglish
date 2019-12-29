<template>
  <main style="height: 100vh">
    <div class="con">
      <img src="@/assets/images/logo.png" alt />

      <div class="dl">
        <div class="d">
          <p
            v-for="(item, i) in pe"
            :key="i"
            @click="d(i)"
            :class="[i == index ? 'p1' : '']"
          >{{ item }}</p>
        </div>

        <div v-show="p">
          <div class="p">
            <p>Mobile Phone Number：</p>
            <el-input v-model="input1" placeholder="Mobile Phone Number"></el-input>
          </div>

          <div class="p">
            <p>Verification Code：</p>
            <el-input v-model="input2" placeholder="Verification Code"></el-input>
            <span>Click to Get</span>
          </div>
          <p @click="dl" class="fh">login</p>
        </div>

        <div class="e" v-show="e">
          <div class="p">
            <p>Email Address：</p>
            <el-input v-model="input3" placeholder="Please enter email address"></el-input>
          </div>

          <div class="p">
            <p>Password：</p>
            <el-input v-model="input4" type="password" placeholder="Please input a password"></el-input>
          </div>
          <p @click="dl" class="fh">login</p>
        </div>
      </div>
    </div>
    <p>
      © China Chamber of Commerce for the Import and Export of Mechanical and
      Electrical products
    </p>
  </main>
</template>

<script>
export default {
  data() {
    return {
      input1: "",
      input2: "",
      input3: "",
      input4: "",
      index: 0,
      p: true,
      e: false,
      pe: ["Login with Mobile Phone Number", "Login with Email Address"]
    };
  },

  methods: {
    dl() {
      this.$router.push("/");
    },

    d(i) {
      if (i == 0) {
        this.p = true;
        this.index = i;
        this.e = false;
      } else {
        this.p = false;
        this.index = i;
        this.e = true;
      }
    }
  }
};
</script>

<style scoped>
.p1 {
  font-size: 15px;
  color: #007aff;
}

.d > p {
  cursor: pointer;
}

main > p {
  text-align: center;
  margin: 25% auto;
  width: 70%;
}

.fh {
  color: #fff;
  background-color: #007aff;
  width: 90%;
  height: 40px;
  line-height: 40px;
  margin: 70px auto 10px;
  text-align: center;
  border-radius: 5px;
  cursor: pointer;
}

.p > span {
  position: absolute;
  top: 192px;
  right: 40px;
  color: #007aff;
  cursor: pointer;
}

.p > p {
  line-height: 40px;
  position: relative;
}

.d {
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.con > .dl {
  padding: 25px;
  background: #fff;
  margin-top: 40px;
  box-shadow: rgba(0, 0, 0, 0.16) 1px 1px 1px 0px;
  border-radius: 2px;
  font-size: 14px;
  position: relative;
  width: 70%;
  margin: auto;
}

.con {
  width: 80%;
  margin: auto;
}

.con > img {
  width: 70%;
  height: 70px;
  display: block;
  margin: auto;
  padding: 80px;
}
</style>
