<template>
  <main style="height: 100vh">
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt />
    <div class="btn">
      <p v-for="(item, i) in btn" :key="i" @click="b(i)">{{ item }}</p>
    </div>
  </main>
</template>

<script>
import myHeader from "@/components/myHeader";
export default {
  components: { myHeader },
  data() {
    return {
      btn: [
        "Enterprise introduction",
        "Forum registration",
        "Contract project declaration",
        "Display project declaration",
        "Interactive introduction",
        "Enterprise display"
      ]
    };
  },
  methods: {
    b(i) {
      if (i == 0) {
        this.$router.push("lunTan");
      } else if (i == 5) {
        this.$router.push("displayList");
      }
    }
  }
};
</script>

<style scoped>
.btn > p {
  border: 1px solid #007aff;
  width: 80%;
  text-align: center;
  border-radius: 5px;
  cursor: pointer;
  margin: 20px auto;
  color: #007aff;
  padding: 13px 0;
}

main {
  background: #fff;
}
</style>
