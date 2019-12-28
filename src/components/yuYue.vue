<template>
  <main>
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">您的位置:</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">首页</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">个人中心</p>
      <p style="margin: 0 10px">></p>
      <p>我的预约</p>
    </div>

    <div class="wdyy">
      <div class="yy">
        <p></p>
        <h4>我的预约</h4>
      </div>
    </div>

    <div v-for="(item, i) in list" :key="i">
      <div class="yn" @click="activity">
        <img :src="item.pic" alt="" />
        <div>
          <h4>{{ item.h4 }}</h4>
          <div>
            <p>{{ item.p1 }}</p>
            <p>{{ item.h6 }}</p>
          </div>
          <h6>{{ item.p2 }}</h6>
        </div>
      </div>
      <div class="xs">
        <div @click="sjxs(item)" v-for="(item, i) in item.xs" :key="i">
          <img
            :src="item.pic"
            v-show="i !== 0 ? image1 == false : image1 == true"
            alt=""
          />
          <img
            :src="item.pic1"
            v-show="i == 0 ? image2 == true : image2 == false"
            alt=""
          />
          <p :class="[i == index ? 'a1' : '']">{{ item.p }}</p>
        </div>
      </div>

      <!-- 时间段显示 -->
      <div class="sjd" v-for="(item, i) in item.sjd" :key="i">
        <p v-show="jj">{{ item.p1 }}</p>
        <div class="nr">
          <img :src="item.pic" alt="" />
          <div @click="details">
            <p>{{ item.p2 }}</p>
            <p>{{ item.p3 }}</p>
          </div>
          <p
            :class="[
              item.p4 == '已预约'
                ? 'yyy'
                : '' || item.p4 == '已拒绝'
                ? 'yjj'
                : ''
            ]"
          >
            {{ item.p4 }}
          </p>
        </div>
        <div class="p5">
          <p>{{ item.p5 }}</p>
          <p v-show="sj">{{ item.p8 }}</p>
        </div>
        <div class="jj">
          <p
            :style="{ marginRight: item.p6 == '取消' ? '-43px' : '' }"
            @click="p6(item)"
          >
            {{ item.p6 }}
          </p>
          <p
            :style="{ background: item.p7 == '拒绝' ? '#ff9800' : '' }"
            @click="p7(item)"
          >
            {{ item.p7 }}
          </p>
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
      sj: false,
      jj: true,
      image1: false,
      image2: true,
      index: 0,
      list: [
        {
          pic: require("@/assets/images/h1.png"),
          h4: "第二届中日第三方市场合作A",
          p1: "2019-11-15",
          h6: "洽谈地址：第七会议室",
          p2: "主论坛拟由双方主办单位负责人作主旨发言经济团体及企代表发言",
          xs: [
            {
              pic: require("@/assets/images/shiJian.png"),
              pic1: require("@/assets/images/shiJianActive.png"),
              p: "时间段显示"
            },
            {
              pic: require("@/assets/images/yaoYueF.png"),
              pic1: require("@/assets/images/yaoYueFActive.png"),
              p: "邀约方显示"
            }
          ],
          sjd: [
            {
              p1: "15:00-15:15",
              pic: require("@/assets/images/h1.png"),
              p2: "Artepharm Co., Ltd., China",
              p3: "电话：010-149146124",
              p4: "待确认",
              p5: "简介：Artepharm Co., Ltd., China",
              p6: "接受",
              p7: "拒绝",
              p8: "预约时间段：15:30-15:45"
            },
            {
              p1: "15:00-15:15",
              pic: require("@/assets/images/h1.png"),
              p2: "Artepharm Co., Ltd., China",
              p3: "电话：010-149146124",
              p4: "已预约",
              p5: "简介：Artepharm Co., Ltd., China",
              p6: "取消",
              p8: "预约时间段：15:30-15:45"
            },
            {
              p1: "15:00-15:15",
              pic: require("@/assets/images/h1.png"),
              p2: "Artepharm Co., Ltd., China",
              p3: "电话：010-149146124",
              p4: "已拒绝",
              p5: "简介：Artepharm Co., Ltd., China",
              p8: "预约时间段：15:30-15:45"
            }
          ]
        },
        {
          pic: require("@/assets/images/h1.png"),
          h4: "第二届中日第三方市场合作B",
          p1: "2019-11-30",
          h6: "洽谈地址：第五会议室",
          p2: "主论坛拟由双方主办单位负责人作主旨发言经济团体及企代表发言",
          xs: [
            {
              pic: require("@/assets/images/shiJian.png"),
              pic1: require("@/assets/images/shiJianActive.png"),
              p: "时间段显示"
            },
            {
              pic: require("@/assets/images/yaoYueF.png"),
              pic1: require("@/assets/images/yaoYueFActive.png"),
              p: "邀约方显示"
            }
          ],
          sjd: [
            {
              p1: "15:00-15:30",
              pic: require("@/assets/images/h1.png"),
              p2: "Artepharm Co., Ltd., China",
              p3: "电话：010-149146124",
              p4: "已拒绝",
              p5: "简介：Artepharm Co., Ltd., China",
              p8: "预约时间段：15:30-15:45"
            },
            {
              p1: "15:00-15:50",
              pic: require("@/assets/images/h1.png"),
              p2: "Artepharm Co., Ltd., China",
              p3: "电话：010-149146124",
              p4: "已拒绝",
              p5: "简介：Artepharm Co., Ltd., China",
              p8: "预约时间段：15:30-15:45"
            }
          ]
        }
      ]
    };
  },

  methods: {
    sy() {
      this.$router.push("/");
    },

    activity() {
      this.$router.push("activity");
    },

    sjxs(i) {
      console.log(this.list[0].xs);

      if (this.list[0].xs) {
        if (i == 0) {
          this.jj = true;
          this.sj = false;
          this.image1 = false;
          this.image2 = true;
          this.index = i;
        } else {
          this.jj = false;
          this.sj = true;
          this.index = i;
          this.image1 = true;
          this.image2 = false;
        }
      }
    },

    details() {
      this.$router.push("details");
    },

    p6(item) {
      if (item.p6 == "接受") {
        this.$message({
          message: "已接受",
          type: "success"
        });
      } else {
        this.$prompt("请输入取消理由", "提示", {
          confirmButtonText: "确定",
          cancelButtonText: "取消"
        })
          .then(({ value }) => {
            this.$message({
              type: "success",
              message: "取消成功"
            });
          })
          .catch(() => {
            this.$message({
              type: "info",
              message: "已取消"
            });
          });
      }
    },

    p7() {
      this.$prompt("请输入拒绝理由", "提示", {
        confirmButtonText: "确定",
        cancelButtonText: "取消"
      })
        .then(({ value }) => {
          this.$message({
            type: "success",
            message: "拒绝成功"
          });
        })
        .catch(() => {
          this.$message({
            type: "info",
            message: "取消拒绝"
          });
        });
    },

    gr() {
      this.$router.push("my");
    }
  }
};
</script>

<style scoped>
.a1 {
  color: #007aff !important;
}

.p5 > p {
  line-height: 20px;
}

.p5 {
  font-size: 14px;
  color: #999;
  margin: 10px 54px;
}

.yyy {
  color: #009688 !important;
  border: 1px dashed #009688 !important;
}

.yjj {
  border: 1px dashed #828282 !important;
  color: #7d7d7d !important;
}

.sjd > .jj > p {
  margin: 0 5px;
  color: #fff;
  background: #2375ff;
  border-radius: 5px;
  line-height: 35px;
  width: 60px;
  cursor: pointer;
  text-align: center;
}

.sjd > .jj > div {
  display: flex;
  align-items: center;
  margin-left: 73px;
}

.sjd > .jj {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  margin-right: 29px;
}

.sjd > .nr > p {
  border: 1px dashed #007aff;
  color: #007aff;
  width: 90px;
  border-radius: 5px;
  text-align: center;
  line-height: 25px;
}

.sjd > .nr > div > p {
  line-height: 25px;
}

.nr > div {
  cursor: pointer;
}

.sjd > .nr {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-top: 20px;
}

.sjd > p {
  color: #999;
  line-height: 30px;
  border-bottom: 1px dashed #c1c1c1;
}

.sjd > div > img {
  border-radius: 100%;
  height: 40px;
  width: 40px;
}

.sjd {
  background: #fff;
  padding: 10px;
  margin: 10px 0;
}

.xs div p {
  font-size: 14px;
  color: #999;
}

.xs div {
  text-align: center;
  cursor: pointer;
}

.xs {
  display: flex;
  background: #fff;
  align-items: center;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;
  justify-content: space-around;
}

.yn > div > h6 {
  font-weight: 400;
  margin-top: 27px;
}

.yn > div > div {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.yn > div > div > p {
  color: #999;
  font-size: 14px;
}

.yn > div > h4 {
  font-weight: 400;
  margin-bottom: 10px;
}

.yn > img {
  width: 30%;
  height: 100px;
  border-radius: 10px;
  float: left;
}

.yn {
  display: flex;
  align-items: center;
  justify-content: space-around;
  background: #fff;
  margin-top: 20px;
  padding: 15px 10px 15px;
  cursor: pointer;
}

.yy {
  display: flex;
  align-items: center;
}

.yy > p {
  width: 5px;
  height: 20px;
  margin-right: 5px;
  background-color: #007aff;
}

.wdyy {
  background: #fff;
  padding: 5px;
  margin: 10px 0 -20px;
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
</style>
