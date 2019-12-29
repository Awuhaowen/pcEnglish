<template>
  <main>
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt />

    <div class="top">
      <img src="@/assets/images/sj.png" alt />
      <p>Enterprise Show</p>
    </div>

    <div class="con" v-for="(item, i) in list" :key="i">
      <p>{{item.p1}}</p>

      <div class="js">
        <div class="s">
          <img :src="item.pic" alt />
          <div @click="zhuanTi">
            <h2>{{item.h2}}</h2>
            <p>{{item.p2}}</p>
          </div>
        </div>

        <div class="x">
          <p>{{item.p3}}</p>
          <span>{{item.s}}</span>
        </div>
      </div>

      <div class="list" v-for="(item, i) in item.con" :key="i">
        <div class="yuan"></div>
        <div class="t">
          <img :src="item.pic" alt />
          <p @click="zhanShi">{{item.p1}}</p>
        </div>

        <div class="yysj">
          <p @click="open">{{item.p2}}</p>
          <p style="color: #e51c23">{{item.p3}}</p>
          <p @click="open">{{item.p4}}</p>
          <p style="color: #007aff">{{item.p5}}</p>
        </div>

        <p>{{item.p5}}</p>
      </div>
    </div>

    <div class="btn">
      <p @click="home">Home</p>
    </div>

    <yq-input :tc.sync="tc" @tj="tiJiao" @fh="fanHui"></yq-input>
    <success :success.sync="success" @chaKan="ck" @qiTa="qt"></success>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";
import yqInput from "@/common/yqInput";
import success from "@/common/success";
export default {
  components: { myHeader, yqInput, success },

  data() {
    return {
      tc: false,
      success: false,
      list: [
        {
          p1: "Recommend",
          pic: require("@/assets/images/h1.png"),
          h2: "The second third market cooperation between China ...",
          p2:
            "main BBS is intended to be issued by the principals of the ponsoring units of",
          p3: "Venue: Tokyo, Japan",
          s: "2019-11-15 12:12:50",

          con: [
            {
              pic: require("@/assets/images/biaoQian.png"),
              p1: "01-Beijing commercial trade co. LTD",
              p2: "15:00-15:15 Open",
              p3: "15:15-15:30 Booked",
              p4: "15:30-15:45 Open",
              p5: "15:45-16:00 confirmed",
              p6:
                "China Energy Engineering Group Guangdong China EnergyEngineering GroupGuangdong"
            },
            {
              pic: require("@/assets/images/biaoQian.png"),
              p1: "02-Beijing commercial trade co. LTD",
              p2: "15:00-15:15 Open",
              p3: "15:15-15:30 Booked",
              p4: "15:30-15:45 Open",
              p5: "15:45-16:00 confirmed",
              p6:
                "China Energy Engineering Group Guangdong China EnergyEngineering GroupGuangdong"
            },
            {
              pic: require("@/assets/images/biaoQian.png"),
              p1: "03-Beijing commercial trade co. LTD",
              p2: "15:00-15:15 Open",
              p3: "15:15-15:30 Booked",
              p4: "15:30-15:45 Open",
              p5: "15:45-16:00 confirmed",
              p6:
                "China Energy Engineering Group Guangdong China EnergyEngineering GroupGuangdong"
            }
          ]
        },
        {
          p1: "Recommend",
          pic: require("@/assets/images/h1.png"),
          h2: "The second third market cooperation between China ...",
          p2:
            "main BBS is intended to be issued by the principals of the ponsoring units of",
          p3: "Venue: Tokyo, Japan",
          s: "2019-11-15 12:12:50",

          con: [
            {
              pic: require("@/assets/images/biaoQian.png"),
              p1: "01-Beijing commercial trade co. LTD",
              p2: "15:00-15:15 Open",
              p3: "15:15-15:30 Booked",
              p4: "15:30-15:45 Open",
              p5: "15:45-16:00 confirmed",
              p6:
                "China Energy Engineering Group Guangdong China EnergyEngineering GroupGuangdong"
            },
            {
              pic: require("@/assets/images/biaoQian.png"),
              p1: "02-Beijing commercial trade co. LTD",
              p2: "15:00-15:15 Open",
              p3: "15:15-15:30 Booked",
              p4: "15:30-15:45 Open",
              p5: "15:45-16:00 confirmed",
              p6:
                "China Energy Engineering Group Guangdong China EnergyEngineering GroupGuangdong"
            }
          ]
        }
      ]
    };
  },

  methods: {
    open() {
      this.tc = true;
    },

    zhuanTi() {
      this.$router.push("zhuanTi");
    },

    zhanShi() {
      this.$router.push("zhanShi");
    },

    ck() {
      this.$router.push("yuYue");
    },

    qt() {
      this.$router.push("displayList");
    },

    home() {
      this.$router.push("/");
    },

    tiJiao() {
      this.tc = false;
      this.success = true;
    },

    fanHui() {
      this.tc = false;
    }
  }
};
</script>

<style scoped>
.btn {
  text-align: center;
  width: 70%;
  cursor: pointer;
  margin: 20px auto;
}

.btn > p {
  line-height: 40px;
  color: #fff;
  background-color: #007aff;
  border-radius: 5px;
  text-align: center;
}

.list > p {
  font-size: 14px;
  color: #999;
  margin-left: 17px;
}

.yysj > p {
  background: #eee;
  width: 45%;
  line-height: 3;
  border-radius: 5px;
  text-align: center;
  margin: 10px 0;
  cursor: pointer;
  color: #009688;
}

.yysj {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  margin-top: 20px;
  align-items: center;
}

.list > .t > p {
  text-align: center;
  color: #999;
  margin-top: -10px;
  cursor: pointer;
}

.list > .t > img {
  width: 20px;
  height: 20px;
}

.list > .t {
  height: 55px;
  border-bottom: 1px solid #eee;
}

.list {
  position: relative;
  padding: 20px;
  background: #fff;
  margin: 5px 0;
}

.list > .yuan {
  width: 40px;
  height: 20px;
  position: absolute;
  left: 50%;
  top: 0;
  margin-left: -20px;
  border-radius: 0 0 100px 100px;
  text-align: center;
  background: #ededed;
}

.con > p {
  padding: 10px 5px;
  color: #007aff;
}

.x > span {
  color: #007aff;
}

.x > p {
  color: #999;
}

.x {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 20px;
}

.js > .s > div > p {
  color: #999;
}

.s > div {
  width: 55%;
  cursor: pointer;
}

.js > .s > div > h2 {
  font-weight: 400;
}

.js > .s > img {
  width: 40%;
  height: 120px;
  border-radius: 5px;
}

.js > .s {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.js {
  background: #fff;
  padding: 20px;
}

.top > p {
  color: #999;
  margin-left: 10px;
}

.top > img {
  width: 30px;
  height: 30px;
}

.top {
  background: #fff;
  padding: 10px;
  display: flex;
  align-items: center;
}
</style>