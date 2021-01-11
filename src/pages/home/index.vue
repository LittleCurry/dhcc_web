<template>
  <div class="home-page">
    <div class="header">
      <homeheader :scroll="true" :style_shade="true" :activeitem="activeitem" :data="bgdata"></homeheader>
    </div>
    <div class="container">
      <div class="left"></div>
      <div class="right"></div>
      <div class="main">
        <frame :data="module_data_10" :limit="7"  :exhibition="true">
        <frame :data="module_data_3" :limit="6">
        <frame :data="module_data_2" :limit="7"  :exhibition="true">
        <frame :data="module_data_5" :limit="6">
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
      activeitem: [true,"","","","",""],
      scroll: 0,
      bgdata: this.$store.state.webData.background.data,
      module_data_10: this.$store.state.webData.module_data_10,
      module_data_2: this.$store.state.webData.module_data_2,
      module_data_3: this.$store.state.webData.module_data_3,
      module_data_5: this.$store.state.webData.module_data_5    
    };
  },
  created() {
    //console.log(this.$store.state.webData.background.data);
    //console.log(this.data);
  },
  mounted() {
  },
  destroyed() {
  },
  methods: {}
};
</script>


<style lang="scss">
@import "./index";
</style>
