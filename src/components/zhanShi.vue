<template>
  <main style="background: #fff;">
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt />

    <h2>Beijing foreign languages commer</h2>
    <div class="a" v-for="(item, i) in a" :key="i">
      <h3>{{item.h3}}</h3>
      <p>{{item.p}}</p>
    </div>

    <div class="b">
      <div v-for="(item, i) in b" :key="i">
        <img :src="item.pic" alt />
        <p>{{item.p}}</p>
      </div>
    </div>

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
          <span>*</span>Your Time Selectionï¼š
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

      <p class="btn" @click="btn">Submission</p>
    </div>

    <div class="footer">
      <div class="tn">
        <p>Return</p>
      </div>
      <p>leave a message:</p>
      <div class="ok">
        <el-input v-model="state" placeholder="请输入内容" style="width: 70%;">
          <i class="el-icon-edit el-input__icon" slot="suffix"></i>
        </el-input>
        <p @click="btn">OK</p>
      </div>
    </div>

    <!-- 弹窗 -->
    <div class="mask" v-show="tc">
      <div class="tc">
        <h2>prompt</h2>
        <p>Submitted successfully</p>
        <div>
          <p @click="ck">view invitation List</p>
          <p @click="qt">invite Another Company</p>
        </div>
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
      input1: "",
      input2: "",
      input3: "",
      input4: "",
      tc: false,
      state: "",
      textarea2: "",
      b: [
        {
          pic: require("@/assets/images/shouCang.png"),
          p: "Contact Person: Wu Guangjian"
        },
        {
          pic: require("@/assets/images/phone.png"),
          p: "Phone Number: +86 020-32118822"
        },
        {
          pic: require("@/assets/images/youXiang.png"),
          p: "Email: qiuhaoxuan@gedi.com.cn"
        }
      ],

      a: [
        {
          h3: "Company Profile",
          p:
            " China Energy Engineering Group Guangdong Electric Power Design Institute (hereinafter called “GEDI”) was founded in 1958. As an internationalengineering and project contracting firm with National Comprehensive Class-A Engineering qualification, GEDI has achieved core strengths of planning and consulting, survey and design, EPC contracting and investment and operation. GEDI is committed to one-stop integrated solution and all-life-cycle management service for our clients at home and abroad in fields of power, nuclear, building, network and telecom, public works."
        },
        {
          h3: "Business Area",
          p: "Energy-Electric Power"
        },
        {
          h3: "Matchmaking Intention",
          p: "Energy-Electric Power"
        }
      ]
    };
  },

  methods: {
    ck() {
      this.$router.push("yuYue");
    },

    btn() {
      this.tc = true;
    },

    qt() {
      this.$router.push("displayList");
    }
  }
};
</script>

<style scoped>
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

.tc {
  z-index: 999;
  background: #fff;
  width: 600px;
  margin: 30% auto;
  padding: 20px;
  animation: go_in 1s;
}

.tc > div > p {
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

.tc > p {
  color: #999;
  line-height: 4;
}

.footer > p {
  color: #999;
}

.footer > .ok > p {
  background: rgba(187, 187, 187, 0.26);
  font-size: 12px;
  border-radius: 50%;
  padding: 10px;
  color: #101010;
}

.footer > .ok {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.tn {
  text-align: center;
  width: 70%;
  cursor: pointer;
  margin: 20px auto;
}

.tn > p {
  line-height: 40px;
  color: #fff;
  background-color: #007aff;
  border-radius: 5px;
  text-align: center;
}

.footer {
  padding: 20px;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 0px 5px 0px;
}

.btn {
  padding: 0 5px;
  border: 1px dashed #007aff;
  font-size: 12px;
  text-align: center;
  line-height: 28px;
  border-radius: 2px;
  color: #007aff !important;
  width: 106px;
  margin-top: 20px !important;
  cursor: pointer;
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
}

.b > div > img {
  width: 25px;
  height: 25px;
  margin-right: 10px;
}

.b > div {
  display: flex;
  align-items: center;
  line-height: 2;
}

.b {
  background: #fff;
  height: 90px;
  padding: 10px;
  border-bottom: 1px solid #eee;
}

.a > p {
  display: inline-block;
  text-align: justify;
  color: #999;
  margin-left: 10px;
  line-height: 1.5;
}

.a > h3 {
  border-left: 5px solid #007aff;
  font-weight: 400;
  line-height: 1.5;
  margin-bottom: 10px;
  padding-left: 10px;
}

.a {
  padding: 10px;
  border-bottom: 1px solid #eee;
}

main > h2 {
  font-weight: 400;
  color: #101010;
  border-bottom: 1px dashed #bbb;
  text-align: center;
  line-height: 2;
}
</style>