<template>
  <main style="background: #fff">
    <my-header></my-header>

    <div class="head">
      <p style="margin-left: 10px;">You are here：</p>
      <p style="color: #007aff; cursor: pointer;" @click="sy">home</p>
      <p style="margin: 0 10px">></p>
      <p style="color: #007aff; cursor: pointer;" @click="gr">Personal Center</p>
      <p style="margin: 0 10px">></p>
      <p>About us</p>
    </div>

    <div class="yy">
      <p></p>
      <h4>About us</h4>
    </div>

    <div class="bd">
      <div>
        <img src="@/assets/images/logo.png" alt />
      </div>

      <h2>Electromechanical</h2>
      <p>
        Established in July 1988, China Chamber of Commerce for import and
        export of mechanical and electrical products (hereinafter referred to
        as "Chamber of Commerce for mechanical and electrical products") is an
        industrial, national and non-profit social organization voluntarily
        formed by various economic organizations registered in the territory
        of the people's Republic of China and engaged in the production,
        import and export trade of mechanical and electrical products and
        related activities.
      </p>
      <p>
        According to Article 56, Chapter 9 of the foreign trade law of the
        people's Republic of China, the responsibilities of the chamber of
        Commerce for import and export are to provide production, marketing,
        information, training and other services related to foreign trade,
        play a coordinating and self-discipline role, apply for relief
        measures for foreign trade according to law, safeguard the interests
        of members and industries, and report members to relevant government
        departments Suggestions on foreign trade and foreign trade promotion
        activities.
      </p>
      <p>
        As the only National Chamber of Commerce in the import and export
        industry of mechanical and electrical products in China, the chamber
        now has nearly 10000 member enterprises, including the leading
        backbone enterprises and a large number of small and medium-sized
        enterprises in the field of mechanical and electrical foreign trade,
        with strong industry representation. In June 2012, the chamber of
        Commerce of mechanical and electrical industry was rated as the
        highest level in China - 5A social organization by the Ministry of
        civil affairs. Established in July 1988, China Chamber of Commerce for
        import and export of mechanical and electrical products (hereinafter
        referred to as "Chamber of Commerce for mechanical and electrical
        products") is an industrial, national and non-profit social
        organization voluntarily formed by various economic organizations
        registered in the territory of the people's Republic of China and
        engaged in the production, import and export trade of mechanical and
        electrical products and related activities.
      </p>
      <p>
        According to Article 56, Chapter 9 of the foreign trade law of the
        people's Republic of China, the responsibilities of the chamber of
        Commerce for import and export are to provide production, marketing,
        information, training and other services related to foreign trade,
        play a coordinating and self-discipline role, apply for relief
        measures for foreign trade according to law, safeguard the interests
        of members and industries, and report members to relevant government
        departments Suggestions on foreign trade and foreign trade promotion
        activities.
      </p>
      <p>
        As the only National Chamber of Commerce in the import and export
        industry of mechanical and electrical products in China, the chamber
        now has nearly 10000 member enterprises, including the leading
        backbone enterprises and a large number of small and medium-sized
        enterprises in the field of mechanical and electrical foreign trade,
        with strong industry representation. In June 2012, the chamber of
        Commerce of mechanical and electrical industry was rated as the
        highest level in China - 5A social organization by the Ministry of
        civil affairs.
      </p>
      <div id="btn">
        <p @click="gr">Return</p>
      </div>
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

.bd > p {
  text-indent: 2em;
  display: inline-block;
  text-align: justify;
  line-height: 1.7;
}

.bd > h2 {
  text-align: center;
  color: #6c6c6c;
}

.bd > div {
  text-align: center;
}

.bd > div > img {
  width: 70%;
  height: 70px;
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
