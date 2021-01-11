<template>
  <div class="fashion-page">
    <div class="header">
      <homeheader :scroll="true" :style_shade="true" :activeitem="activeitem" :data="bgdata"></homeheader>
    </div>
    <div class="container">
      <div class="left"></div>
      <div class="right"></div>
      <div class="main">
        <frame :data="module_data_1" :limit="14">
        <frame :data="module_data_2" :limit="14">
      </div>
    </div>
    <div class="footer">
      <div class="line"></div>
      <footbar></footbar>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      activeitem: ["", "", "", true, "", ""],
      bgdata: this.$store.state.webData.background.data,
      module_data_1: this.$store.state.webData.module_data_1,
      module_data_2: this.$store.state.webData.module_data_2
    };
  },
  created() {},
  methods: {}
};
</script>


<style lang="scss">
.fashion-page {
  width: 100%;
  /*min-width: 1050px;*/
  height: 100%;

  .header {
    width: 100%;

    .navbar {
      width: 100%;
      position: fixed;
      top: 0;
      z-index: 3;
    }

    .hottags {
      width: 100%;
      margin-top: 55px;
    }
  }

  .container {
    width: 100%;

    .left,
    .right {
      width: 7%;
      height: 0;
      position: absolute;
    }

    .left {
      left: 0;
      //background-color: blue;
      background-color: #FFF;
    }

    .right {
      right: 0;
      //background-color: red;
      background-color: #FFF;
    }

    .main {
      margin: 55px 7%;
      height: 100%;
    }
  }

  .footer {
    width: 100%;

    .line {
      width: 100%;
      height: 2px;
      margin: 0;
      padding: 0;
      background: rgba(255, 85, 0, 1);
    }
  }
}
</style>
