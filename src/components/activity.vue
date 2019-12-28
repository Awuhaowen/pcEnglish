<template>
  <main>
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt="" />
    <div class="head">
      <h4>活动专题：第二届中日第三方市场合作论坛</h4>
      <div>
        <p>2019-09-25 888人参与</p>
        <span v-show="cjcg">参加成功</span>
      </div>
    </div>

    <div class="main">
      <div>
        <p style="color: #6c6c6c">【会议地点】</p>
        <p>● 第八会议室</p>
        <p style="color: #6c6c6c">【活动中心】</p>
        <p>● 论坛拟于2020年4月上旬（暂定）在日本东京举行</p>
        <p>● 论坛由主论坛和分论坛两部分组成。</p>
        <p style="color: #6c6c6c">【活动内容】</p>
        <div class="nr">
          <p>
            主论坛拟由双方主办单位负责人作主旨发言，经济团体及企业代表发言，相关政府部门、经济团体、金融机构和企业代表参会。配套举行成果展示，以展板形式展示中日第三方市场合作重点项目。
          </p>
          <p>
            分论坛拟在主论坛前日举行，包括交通物流、能源环保、产业升级和金融支持、地区开发4个专题暂定,分论坛，采取主题发言和研讨相结合的形式，探讨合作思路和模式。会间或会后配套举行商务洽谈和对接活动。
          </p>
        </div>
      </div>
      <el-button
        type="text"
        style="color: #007aff;
               text-align: center;
               font-size: 16px;
               border: 1px dashed #007aff;
               border-radius: 5px;
               margin: 30px 55px;
               width: 80%;"
        @click="open"
        v-show="cjyy"
      >
        参加邀约
      </el-button>
      <!-- <p @click="yy">参加邀约</p> -->
    </div>
    <!-- 
    <div class="footer">
      <div>
        <h1></h1>
        <h6>为落实中日两国领导人重要共识，经双方商定，经双方商定</h6>
        <p>专题</p>
      </div>

      <p>
        主论坛拟由双方主办单位负责人作主旨发言，经济团体及企业代
        表发言，相关政府部门、经济团体.....
      </p>
    </div> -->

    <p @click="fanHui">返回首页</p>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";
export default {
  components: { myHeader },
  data() {
    return {
      cjcg: false,
      cjyy: true
    };
  },

  methods: {
    fanHui() {
      this.$router.push("/");
    },

    open() {
      this.$confirm(
        `● 参加邀约后会以短信 或者 邮件的方式提醒组办方。
         ● 参加邀约后您在个人中心的状态也会改变`,
        "是否参加邀约",
        {
          confirmButtonText: "是",
          cancelButtonText: "否",
          type: "warning"
        }
      )
        .then(() => {
          this.$message({
            type: "success",
            message: "参加成功!"
          });
          this.cjcg = true;
          this.cjyy = false;
        })
        .catch(() => {
          this.$message({
            type: "info",
            message: "已取消参加"
          });
        });
    }
  }
};
</script>

<style scoped>
main > p {
  color: #fff;
  background-color: #007aff;
  font-size: 16px;
  text-align: center;
  margin: 40px auto;
  border-radius: 8px;
  width: 80%;
  cursor: pointer;
  padding: 10px;
}

.footer > p {
  font-size: 12px;
  color: rgb(204, 204, 204);
  margin-top: 10px;
}

.footer > div {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 0.5px dashed rgb(187, 187, 187);
  height: 60px;
}

.footer > div > p {
  color: #fff;
  background-color: #007aff;
  display: inline-block;
  line-height: 2.3;
  font-size: 13px;
  padding: 0 1.34em;
  border-radius: 5px;
}

.footer > div > h6 {
  font-size: 12px;
  color: rgb(72, 72, 72);
  margin: 0 10px;
}

.footer > div > h1 {
  width: 40px;
  height: 40px;
  background-color: rgb(236, 236, 236);
  border-radius: 80px;
}

.footer {
  background: #fff;
  padding: 10px;
}

.main > p {
  color: #007aff;
  text-align: center;
  padding: 9px 0px;
  font-size: 16px;
  border: 1px dashed #007aff;
  border-radius: 5px;
  margin: 30px auto;
  width: 80%;
}

.main > div > .nr > p {
  text-indent: 2em;
}

.main {
  background: #fff;
  padding: 10px;
  margin: 10px 0;
}

.main > div p {
  font-size: 14px;
  line-height: 30px;
  color: #545454;
}

.head > div {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.head > div > p {
  font-size: 12px;
  color: #999;
}

.head > div > span {
  background: #007aff;
  color: #ffffff;
  font-size: 14px;
  padding: 3px 15px;
  border-radius: 5px;
}

.head > h4 {
  color: rgb(16, 16, 16);
  margin-bottom: 10px;
}

.head {
  background: #fff;
  padding: 10px;
}
</style>
