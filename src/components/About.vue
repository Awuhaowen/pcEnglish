<template>
  <main style="background: #fff">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">您的位置:</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">首页</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">个人中心</p>
      <p style="margin: 0 10px">></p>
      <p>关于我们</p>
    </div>

    <div class="yy">
      <p></p>
      <h4>关于我们</h4>
    </div>

    <div class="bd">
      <img src="@/assets/images/bd_logo.png" alt="" />
      <p>
        “百度——全球最大的中文搜索引擎及最大的中文网站,全球领先的人工智能公司。2000年1月1日创立于中关村公司创始人李彦宏拥有“超链分析”技术专利,使中国成为美国罗斯、韩国之外,全球仅有的四个拥有独立搜索引擎核心技术的国家之一。基于对人工智能的多年布局与长期积累,百度在深度学习领域领先世界,并在2016年被《财富》杂志称为全球AI四巨头之一。每天,百度响应来自百余个国家和地区的数十亿次搜索请求。百度以“用科技让复杂的世界更简单”为使命,不断坚持技创新,致力于提供更懂用户的产品及服务。百度移动应用月活跃设备数超过11亿。百度以技术为信仰,在技术研发、人才引进等方面坚持长期持续的投入。根据中国专利保护协会2018年统计,百度以2368件申请量成为中国人工智能专利领头羊。
        在“夯实移动基础,决胜AI时代”的战略指导...”
      </p>

      <h4 @click="gr">返回</h4>
    </div>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";
export default {
  components: { myHeader },
  data() {
    return {};
  },

  methods: {
    sy() {
      this.$router.push("/");
    },

    gr() {
      this.$router.push("my");
    }
  }
};
</script>

<style scoped>
.bd > h4 {
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

.bd > p {
  text-indent: 2em;
}

.bd > img {
  width: 100%;
  height: 200px;
}

.bd {
  background: #fff;
  padding: 10px;
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
}

.yy > p {
  width: 5px;
  height: 20px;
  margin-right: 5px;
  background-color: #007aff;
}
</style>
