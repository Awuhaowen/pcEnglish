<template>
  <main>
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt="" />
    <div class="head">
      <div>
        <h4>活动主题</h4>
        <p>为落实中日两国领导人重要共识，经双方商定，经双方商定</p>
        <h5>2019-09-22 18:30</h5>
      </div>
    </div>

    <div class="main" v-for="(item, i) in main" :key="i">
      <div class="m">
        <div class="ms" @click="cj">
          <img :src="item.pic1" alt="" />
          <div>
            <h4>{{ item.h4 }}</h4>
            <p>{{ item.p1 }}</p>
          </div>
          <p>{{ item.p2 }}</p>
        </div>

        <p>{{ item.p3 }}</p>

        <div class="pf">
          <div>
            <img :src="item.pic2" alt="" />
            <p>{{ item.p4 }}</p>
            <h5>{{ item.h5 }}</h5>
          </div>
        </div>
      </div>

      <div class="x">
        <p @click="cj">{{ item.p5 }}</p>
        <span>{{ item.s }}</span>
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
      main: [
        {
          pic1: require("@/assets/images/h1.png"),
          h4: "第二届中日第三方市场A 第二届中日第三方市场A",
          p1: "会议地点 第八会议室",
          p2: "热门",
          p3: "主论坛拟由双方主办单位负责人作主旨发言，经济团体及企业代表发言",
          pic2: require("@/assets/images/xing.png"),
          p4: "4.8",
          h5: "426人参加",
          p5: "参加邀约",
          s: "2019-11-15 18:30"
        },
        {
          pic1: require("@/assets/images/h1.png"),
          h4: "第二届中日第三方市场A 第二届中日第三方市场B",
          p1: "会议地点 第六会议室",
          p2: "热门",
          p3: "主论坛拟由双方主办单位负责人作主旨发言，经济团体及企业代表发言",
          pic2: require("@/assets/images/xing.png"),
          p4: "5.0",
          h5: "500人参加",
          p5: "参加邀约",
          s: "2019-11-15 18:30"
        }
      ]
    };
  },

  methods: {
    cj() {
      this.$router.push("activity");
    }
  }
};
</script>

<style scoped>
.x > span {
  font-size: 12px;
  color: #999;
}

.x > p {
  color: #2375ff;
  width: 65px;
  height: 22px;
  border: 1px dashed #2375ff;
  border-radius: 15px;
  text-align: center;
  cursor: pointer;
  line-height: 22px;
}

.x {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 12px;
  background: #fff;
  margin: -9px 10px;
  padding: 15px;
  border-top-right-radius: 15px;
  border-top-left-radius: 15px;
}

.pf > div > h5 {
  color: #8c8c8c;
  margin-left: 40px;
}

.pf > div > img {
  height: 18px;
  margin-right: 10px;
}

.pf > div > p {
  color: #ff9800;
  font-size: 15px;
}

.pf > div {
  display: flex;
  align-items: center;
}

.main > .m > p {
  margin: 20px 0;
}

.main > .m > .ms > p {
  font-size: 12px;
  color: #fff;
  background: #007aff;
  width: 54px;
  height: 23px;
  text-align: center;
  line-height: 23px;
  border-radius: 3px;
}

.main > .m > .ms > div > p {
  color: #999;
  font-size: 12px;
  text-align: center;
}

.main > .m > .ms > div > h4 {
  font-weight: 400;
}

.main > .m > .ms > img {
  border-radius: 100%;
  width: 50px;
  height: 50px;
}

.main > .m > .ms {
  display: flex;
  align-items: center;
  justify-content: space-between;
  cursor: pointer;
}

.main {
  padding: 20px;
}

.main > .m {
  background: #fff;
  margin: 10px;
  padding: 15px;
  border-bottom-right-radius: 15px;
  border-bottom-left-radius: 15px;
}

.head > div > h5 {
  color: #999;
  text-align: right;
  font-weight: 400;
  font-size: 12px;
  margin: 10px 0;
}

.head > div > p {
  color: #999999;
  font-size: 12px;
}

.head > div > h4 {
  font-weight: 400;
  font-size: 18px;
  margin-bottom: 10px;
}

.head {
  background: #fff;
}

.head > div {
  padding: 7px 15px;
}
</style>
