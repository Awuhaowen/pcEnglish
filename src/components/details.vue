<template>
  <main>
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">您的位置:</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">首页</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">个人中心</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;">我的预约</p>
      <p style="margin: 0 10px">></p>
      <p>公司详情</p>
    </div>

    <div class="con">
      <div class="h">
        <h2>Artepharm Co., Ltd., China</h2>
      </div>

      <div class="xx">
        <div class="yy">
          <p></p>
          <h4>基本信息</h4>
        </div>
        <p>洽谈时间： 2019-11-15 10：30-11：00</p>
        <p>洽谈地点: 第七会议室</p>
      </div>

      <div class="yyzt">
        <div class="yy">
          <p></p>
          <h4>预约状态</h4>
        </div>
        <div class="zc">
          <div class="zt">
            <h6>状态：</h6>
            <p>待确认</p>
          </div>
          <div class="cz">
            <h6>操作：</h6>
            <p>接受</p>
            <p style="background: #ff9800;">拒绝</p>
          </div>
        </div>
      </div>

      <div class="qy">
        <div class="yy">
          <p></p>
          <h4>企业介绍</h4>
        </div>
        <p>
          China Energy Engineering Group Guangdong Electric Power Design
          Institute (hereinafter called “GEDI”) was founded in 1958. As an
          international engineering and project contracting firm with National
          Comprehensive Class-A Engineering qualification, GEDI has achieved
          core strengths of planning and consulting, survey and design, EPC
          contracting and investment and operation. GEDI is committed to
          one-stop integrated solution and all-life-cycle management service for
          our clients at home and abroad in fields of power, nuclear, building,
          network and telecom, public works.
        </p>
      </div>

      <div class="lx">
        <div class="yy">
          <p></p>
          <h4>联系方式</h4>
        </div>

        <div class="r">
          <p>联系人：张小小</p>
          <p>电话：15030349874</p>
          <p>邮箱：8756@163.com</p>
        </div>
      </div>

      <div class="ly">
        <div class="yy">
          <p></p>
          <h4>留言</h4>
        </div>

        <p>
          Agriculture processing company looking for development and investment
          support to develop Cocoa, Coconuts, Noni exports
        </p>
      </div>
    </div>

    <p @click="fanHui">返回</p>
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

    fanHui() {
      this.$router.push('yuYue')
    },

    gr() {
      this.$router.push("my");
    }
  }
};
</script>

<style scoped>
main > p {
  margin: 25px auto;
  height: 41px;
  line-height: 41px;
  color: #fff;
  background-color: #007aff;
  text-align: center;
  width: 80%;
  cursor: pointer;
  border-radius: 5px;
}

.ly {
  background: #fff;
  margin: 10px 0;
  padding: 10px;
}

.ly > p {
  font-size: 14px;
  color: #9d9d9d;
  line-height: 25px;
}

.lx > .r {
  font-size: 14px;
  color: #9d9d9d;
  line-height: 25px;
}

.lx {
  background: #fff;
  margin: 10px 0;
  padding: 10px;
}

.qy {
  background: #fff;
  margin: 10px 0;
  padding: 10px;
}

.qy > p {
  font-size: 14px;
  color: #9d9d9d;
  line-height: 20px;
}

.cz > p {
  display: inline-block;
  line-height: 2.3;
  font-size: 13px;
  padding: 0 1.34em;
  color: #fff;
  background-color: #007aff;
  border-radius: 5px;
  margin: 0 10px;
}

.zt > p {
  width: 63px;
  border: 1px dashed #007aff;
  color: #007aff;
  font-size: 14px;
  text-align: center;
  line-height: 26px;
  margin-right: 45px;
}

.yyzt > .zc > div > h6 {
  color: #9d9d9d;
  font-size: 14px;
}

.zc {
  display: flex;
  align-items: center;
}

.zt {
  display: flex;
  align-items: center;
}

.yyzt {
  background: #fff;
  margin: 10px 0;
  padding: 10px;
}

.cz {
  display: flex;
  align-items: center;
}

.xx > p {
  font-size: 14px;
  color: #5e5e5e;
}

.h > h2 {
  font-weight: 400;
}

.xx {
  background: #fff;
  margin-bottom: 10px;
  padding: 10px;
}

.h {
  line-height: 50px;
  text-align: center;
  border-bottom: 2px dashed #bbbbbb;
  margin-top: 10px;
  background: #fff;
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
  line-height: 40px;
}

.yy > h4 {
  font-weight: 400;
  color: #777;
}

.yy > p {
  width: 5px;
  height: 20px;
  margin-right: 5px;
  background-color: #007aff;
}
</style>
