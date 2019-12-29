<template>
  <main>
    <my-header></my-header>
    <img style="width: 100%;" src="@/assets/images/h1.png" alt />

    <div class="con">
      <p style="text-indent: 2rem">
        In order to implement the important consensus reached by the leaders of
        China and Japan, the two sides agreed to conduct business，Ministry,
        National Development and Reform Commission, ministry of economy, trade
        and industry, Ministry of Foreign AffairsCo-host the second china-japan
        third party market cooperation BBS (hereinafter referred to as
        "BBS")BBS)).The relevant matters are hereby notified as follows:
      </p>
      <h5>One, BBS session</h5>
      <p>
        BBB 0 will be held in Tokyo, Japan in early April 2020 (tentative)The
        specific time and place will be further notified.
      </p>
      <h5>Ii. BBS arrangement</h5>
      <p>BBS is composed of main BBS and sub BBS.</p>
      <p>
        Main BS proposed by the two sides to host the unit responsible person to
        make a keynote speech, economicGroup and enterpriserepresentatives
        spoke, relevant government departments, economic groups, jinFinancial
        institutions and business representatives attend the meeting.Supporting
        the holding of results display todisplay boardTo show the key projects
        of the third market cooperation between China and Japan.
      </p>
      <h5>3. Related matters</h5>
      <p>
        (a) please confirm the participants as soon as possible, combined with
        functional development
      </p>
      <p>
        Develop policy recommendations on third party market cooperation between
        China and Japan, and recommend goods in transportation
      </p>
      <p>
        Flow, energy and environmental protection, industrial upgrading
        (industrial parks, smart cities, things
      </p>
      <p>
        Representative business owners with solid achievements in cooperation
        with Japan in areas such as trade cooperation zone
      </p>
      <p>
        2. All units are requested to recommend products in line with the state
        administration of industry and foreign economic cooperation
      </p>
      <p>
        Policy, with a certain scale and demonstration, mature negotiation of
        high quality draft
      </p>
      <p>
        About the cooperation project and recommend the project to show the
        results.
      </p>
      <p>
        (3) five Chinese representatives and two Chinese representatives will be
        arranged for each BBS
      </p>
      <p>
        Representatives to participate in the interactive discussion, please
        recommend the industry representative
      </p>
      <p>
        Enterprise, as a spokesman, and organize enterprises to attend 冾
        docking
      </p>
      <p>Will talk about.</p>
      <p>(iv) please report through BBS before December 6, 2019</p>

      <div class="x">
        <p>Name "and" sign and show project declaration "port, submit all online</p>
        <p>
          Detailed information of participants, declaration of the proposed
          signing or exhibition project;
        </p>
        <p>At the same time the</p>
        <p>
          Attached is the registration receipt and BBS spokesman information
          form
        </p>
        <p>
          After stamping the official seal back to the mechanical and electrical
          chamber of commerce, and copy the Asian department of commerce, he
        </p>
        <p>As a company.</p>
      </div>

      <div class="f">
        <h4>accessory：</h4>
        <p>1. Receipt of registration (with official seal)</p>
        <p>2. BBS spokesman information table</p>
      </div>
      <div id="btn" @click="fh">
        <p>Home</p>
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
    fh() {
      this.$router.push("/");
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

.con > .f {
  height: 80px;
  line-height: 1.5;
  border-bottom: 1px dashed #bbb;
}

.con > .x {
  font-weight: 600;
  display: inline-block;
  text-align: justify;
  line-height: 1.5;
}

.con {
  background: #fff;
  padding: 20px;
}

.con > h5 {
  font-weight: 400;
  font-size: 14px;
  color: #101010;
  line-height: 3;
}

.con > p {
  color: #484848;
  font-size: 14px;
  display: inline-block;
  text-align: justify;
}
</style>