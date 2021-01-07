<template>
  <div class="about-page">
    <div class="header">
      <navbar :scroll="false" :style_shade="false" :menu_v="false" :extend="false" :activeitem="activeitem"></navbar>
    </div>
    <div class="container">
      <div class="about-title">
        <p>关于DHCC</p>
      </div>
      <div class="about-content">
        <div class="about-left"></div>
        <div class="about-right"></div>
        <div class="about-main">
          <p>{{content[0]}}</p>
          <p>{{content[1]}}</p>
          <p>{{content[2]}}</p>
        </div>
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
      content: [
        "DHCC 网站"
      ],
      activeitem: ["","","","","","",""]
    };
  },
  methods: {}
};
</script>


<style lang="scss">
@import "./index";
</style>
