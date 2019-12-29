<template>
  <main style="height: 100vh">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">You are here：</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">home</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">personal center</p>
      <p style="margin: 0 10px">></p>
      <p>My Bookingss</p>
    </div>

    <div class="wdyy">
      <div class="yy">
        <p></p>
        <h4>My Bookings</h4>
      </div>
    </div>

    <div class="con" v-for="(item, i) in con" :key="i">
      <div class="s">
        <img :src="item.pic" alt />
        <div @click="details">
          <h3>{{item.h3}}</h3>
          <p>{{item.p1}}</p>
        </div>
      </div>
      <div class="x">
        <h6>{{item.h6}}</h6>
        <div>
          <p @click="p(item)">{{item.p2}}</p>
          <span
            :class="[
              item.s == 'Successful operation' 
              ? 't1' 
              : item.s == 'operation failed' 
              ? 't2' 
              : ''
            ]"
          >{{item.s}}</span>
        </div>
      </div>
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
      con: [
        {
          pic: require("@/assets/images/h1.png"),
          h3: "Beijing foreign languages commercial trade co. LTD",
          p1: "Place of negotiation : Glory Oriental...",
          h6: "Invitation time : 15:15-15:30",
          p2: "Cancel",
          s: "To be confirmed"
        },
        {
          pic: require("@/assets/images/h1.png"),
          h3: "Beijing foreign languages commercial trade co. LTD",
          p1: "Place of negotiation : Glory Oriental...",
          h6: "Invitation time : 15:15-15:30",
          p2: "Cancel",
          s: "Successful operation"
        },
        {
          pic: require("@/assets/images/h1.png"),
          h3: "Beijing foreign languages commercial trade co. LTD",
          p1: "Place of negotiation : Glory Oriental...",
          h6: "Invitation time : 15:15-15:30",
          p2: "Invite again",
          s: "operation failed"
        }
      ]
    };
  },

  methods: {
    sy() {
      this.$router.push("/");
    },

    ck() {
      this.$router.push("yuYue");
    },

    qt() {
      this.$router.push("displayList");
    },

    details() {
      this.$router.push("details");
    },

    p(item) {
      if (item.p2 == "Cancel") {
        this.$confirm(
          "Do you want to cancel this invitation?",
          "notification",
          {
            confirmButtonText: "YES",
            cancelButtonText: "NO"
            // type: "warning"
          }
        );
        // .then(() => {
        //   this.$message({
        //     type: "success",
        //     message: "删除成功!"
        //   });
        // })
        // .catch(() => {
        //   this.$message({
        //     type: "info",
        //     message: "已取消删除"
        //   });
        // });
      } else {
        this.tc = true;
      }
    },

    tiJiao() {
      this.tc = false;
      this.success = true;
    },

    fanHui() {
      this.tc = false;
    },

    gr() {
      this.$router.push("my");
    }
  }
};
</script>

<style scoped>
.t2 {
  border-color: #bbbbbb !important;
  color: #5b5b5b !important;
}

.t1 {
  border-color: #009688 !important;
  color: #009688 !important;
}

.x > div > span {
  padding: 0 1.34em;
  border: 1px dashed #007aff;
  font-size: 12px;
  text-align: center;
  line-height: 2.2;
  border-radius: 2px;
  color: #007aff;
}

.x > div > p {
  display: inline-block;
  line-height: 2.3;
  margin-right: 20px;
  font-size: 13px;
  color: #fff;
  cursor: pointer;
  background-color: #007aff;
  border-radius: 5px;
  padding: 0 1.34em;
}

.x > h6 {
  color: #999;
  font-weight: 400;
}

.x > div {
  display: flex;
  align-items: center;
}

.x {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
}

.s > div > p {
  font-size: 14px;
  color: #999;
  margin: 10px 0;
}

.s > div {
  width: 57%;
  cursor: pointer;
}

.s > div > h3 {
  font-weight: 400;
}

.con > .s > img {
  width: 170px;
}

.con {
  background: #fff;
  padding: 10px;
  margin: 10px 0;
}

.con > .s {
  display: flex;
  align-items: center;
  justify-content: space-around;
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
  padding: 10px;
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
</style>
