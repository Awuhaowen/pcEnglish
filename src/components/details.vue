<template>
  <main>
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt />

    <div class="top">
      <h3>Beijing foreign languages commercial trade co. LTD</h3>
      <div>
        <p>Invitation time : 14:30-14:45</p>
      </div>
      <h6>Place of negotiation : Glory Orientalam B</h6>
    </div>

    <div class="con">
      <h3 style="margin-bottom: 5px">【Invitation status】</h3>
      <div>
        <p>status：to be confirmed</p>
        <div>
          operating：
          <p>operation</p>
        </div>
      </div>
      <h3>【Company Profile】</h3>
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
      <h3>【Business Area】</h3>
      <p>Energy-Electric Power</p>
      <h3>【Matchmaking Intention】</h3>
      <p>Energy-Electric Power</p>
    </div>

    <div class="x">
      <p>Contact Person: Wu Guangjian</p>
      <p>Phone Number: +86 020-32118822</p>
      <p>Email: qiuhaoxuan@gedi.com.cn</p>
    </div>

    <div id="btn">
      <p @click="fanHui">return</p>
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
    fanHui() {
      this.$router.push("yuYue");
    }
  }
};
</script>

<style scoped>
#btn {
  text-align: center;
  width: 70%;
  cursor: pointer;
  margin: 20px auto;
}

#btn > p {
  line-height: 40px;
  color: #fff;
  background-color: #007aff;
  border-radius: 5px;
  text-align: center;
}

.x {
  padding: 10px;
}

.x > p {
  color: #007aff;
  line-height: 1.5;
}

.con > div {
  display: flex;
  align-items: center;
  color: #999;
  margin-left: 20px;
  justify-content: space-between;
}

.con > div > div > p {
  width: 86px;
  padding: 0;
  color: #fff;
  background-color: #007aff;
  display: inline-block;
  line-height: 2.3;
  font-size: 13px;
  text-align: center;
  border-radius: 5px;
}

.con > div > div {
  display: flex;
  align-items: center;
}

.con > p {
  color: #999;
  display: inline-block;
  text-align: justify;
  margin-left: 20px;
}

.con > h3 {
  font-weight: 400;
  line-height: 1.9;
}

.con {
  background: #fff;
  padding: 10px;
}

.top > h6 {
  text-align: right;
  color: #999;
}

.top > div {
  display: flex;
  justify-content: flex-end;
  margin: 20px 0;
}

.top > div > p {
  width: 33%;
  height: 30px;
  font-size: 14px;
  line-height: 30px;
  text-align: center;
  border-radius: 3px;
  background-color: #007aff;
  color: #fff;
}

.top > h3 {
  font-weight: 400;
}

.top {
  background: #fff;
  padding: 10px;
}
</style>
