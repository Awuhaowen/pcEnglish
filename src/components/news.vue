<template>
  <main style="height: 100vh;">
    <div class="head">
      <img src="@/assets/images/fanHui.png" @click="fanHui" alt="" />

      <div>
        <p
          :style="{
            margin: i == 0 ? '0 150px' : ''
          }"
          v-for="(item, i) in xt"
          :key="i"
          @click="head(i)"
          :class="[i == index ? 'xz' : '']"
        >
          {{ item }}
        </p>
      </div>
    </div>

    <div class="con" v-for="(item, i) in con" :key="i" @click="c" v-show="xx">
      <p>{{ item.p1 }}</p>
      <div>
        <p>{{ item.p2 }}</p>
        <p>{{ item.p3 }}</p>
      </div>
    </div>

    <div class="tz" v-show="tz">
      <img src="@/assets/images/tongZhi.png" alt="">
      <p>暂无通知</p>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      xx: true,
      tz: false,
      index: 0,
      xt: ["消息", "通知"],
      con: [
        {
          p1: "Baidu",
          p2:
            "@Artepharm Co., Ltd., China您好。你关注的第二届中日第三方市场合作论坛",
          p3: "2019-11-15 12:12:50"
        },
        {
          p1: "头条",
          p2:
            "@Artepharm Co., Ltd., China您好。你关注的第二届中日第三方市场合作论坛",
          p3: "2019-11-15 16:10:30"
        },
        {
          p1: "Baidu",
          p2:
            "@Artepharm Co., Ltd., China您好。你关注的第二届中日第三方市场合作论坛",
          p3: "2019-11-15 12:12:50"
        }
      ]
    };
  },
  methods: {
    head(i) {
      if (i == 0) {
        this.xx = true;
        this.tz = false;
        this.index = i;
      } else {
        this.tz = true;
        this.xx = false;
        this.index = i;
      }
    },

    c() {
      this.$router.push("notice");
    },

    fanHui() {
      this.$router.push("/");
    }
  }
};
</script>

<style scoped>
.con > p {
  font-size: 16px;
  color: #757575;
  line-height: 2;
}

.con > div > p:first-of-type {
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
  width: 50%;
}

.con > div {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #5e5e5e;
  font-size: 14px;
}

.con {
  background: #fff;
  padding: 10px 20px;
  border-bottom: 1px solid #eee;
  cursor: pointer;
}

.xz {
  color: #007aff;
}

.tz {
  text-align: center;
  margin-top: 50%;
}

.tz > img {
  width: 100px;
  height: 100px;
}

.head > div {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.head {
  display: flex;
  align-items: center;
  padding: 10px;
  background: #fff;
}

.head > img {
  width: 20px;
  cursor: pointer;
  height: 20px;
}
</style>
