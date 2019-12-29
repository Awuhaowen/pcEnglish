<template>
  <main>
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt />

    <div class="con" v-for="(item, i) in con" :key="i">
      <div>
        <p></p>
        <h2>{{item.h2}}</h2>
      </div>
      <p>{{item.p}}</p>
    </div>

    <div id="btn">
      <p @click="gr">return</p>
    </div>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";
export default {
  components: { myHeader },
  data() {
    return {
      con: [
        {
          h2: "Thematic name",
          p:
            "The second China Japan third party market a the second China Japan third party market a"
        },
        {
          h2: "Thematic time",
          p: "2019-11-15 18:30"
        },
        {
          h2: "Thematic location",
          p:
            "Science and technology development building, Peking University, Guangdong Province"
        },
        {
          h2: "Introduction",
          p:
            "The main forum will be made by the heads of the host units of both sides, and the representatives of economic organizations and enterprises will make speeches"
        }
      ]
    };
  },

  methods: {
    gr() {
      this.$router.push("displayList");
    }
  }
};
</script>

<style scoped>
#btn {
  text-align: center;
  width: 70%;
  cursor: pointer;
  margin: 38px auto;
}

#btn > p {
  line-height: 40px;
  color: #fff;
  background-color: #007aff;
  border-radius: 5px;
  text-align: center;
}

.con {
  background: #fff;
  padding: 10px;
  border-bottom: 1px solid #eee;
}

.con > p {
  color: #999;
  margin-left: 12px;
}

.con > div {
  display: flex;
  align-items: center;
}

.con > div > h2 {
  font-weight: 400;
  margin-left: 5px;
  line-height: 2;
}

.con > div > p {
  width: 5px;
  height: 24px;
  margin-right: 15upx;
  background-color: #007aff;
}
</style>