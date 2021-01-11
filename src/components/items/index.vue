<template>
  <div
    class="items"
    ref="item"
    :id="data.id"
    v-bind:class="{'items-large':isLarge,'items-small':isSmall}"
    @click="linkToPlayer(data)"
    @mouseover="mouseIn()"
    @mouseout="mouseOut()"
  >
    <div class="items-bg" v-if="isLarge">
      <div class="items-cover">
        <img alt="bmp" :src="data.cover">
      </div>
      <p v-bind:class="{'items-selected':isHover}">{{data.title}}</p>
    </div>

    <div class="items-bg" v-if="!isLarge">
      <div class="items-cover">
        <img alt="bmp" :src="data.poster">
      </div>
      <p v-bind:class="{'items-selected':isHover}">{{data.title}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "items",
  props: {
    isLarge: { type: Boolean, default: false },
    isSmall: { type: Boolean, default: false },
    data: Object,
    rheight: Number,
    rwidth: Number
  },
  data() {
    return {
      isHover: false
    };
  },
  methods: {
    mouseIn() {
      this.isHover = true;
    },
    mouseOut() {
      this.isHover = false;
    },
    getDetails(e) {
      console.log(e.target.getAttribute("test"));
      console.log(e.target.getAttribute("url"));
      console.log(e.target.getAttribute("id"));
      let ele = this.$refs.item;
      console.log(ele.id + "-" + ele.url);
    },
    linkToPlayer(obj) {
      let testData = {
        title: obj.title,
        poster: obj.poster,
        amount: obj.amount,
        source: [
          {
            withCredentials: false,
            type: obj.type,
            // src: obj.video_url
            src: require(obj.video_url)
          }
        ]
      };
      this.$router.push({
        path: "/player",
        query: { data: testData }
      });
    }
  },
  watch: {}
};
</script>

<style lang="scss" scoped>
.items-large {
  width: 92% !important;
  min-height: 230px !important;
  margin-bottom: 0 !important;
  margin-right: 0.64% !important;
  margin-left: 0.64% !important;

  .items-bg {
    p {
      font-size: 20px !important;
      font-weight: bold !important;
    }
  }
}

.items-small {
  /*width: 18% !important;*/
  width: 27% !important;
  margin-right: 1% !important;
  margin-left: 1% !important;
}

.items-selected {
  color: rgba(255, 186, 116, 1) !important;
}

.items {
  /*width: 13%;*/
  width: 30%;
  height: auto;
  margin-right: 0.64%;
  margin-left: 0.64%;
  margin-bottom: 10px !important;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  cursor: pointer;

  .items-bg {
    border: none;
    border-radius: 5px;
    background-color: rgb(243, 243, 243);

    .items-cover {
      width: 100%;
      height: 100%;

      img {
        width: 100%;
        border-top-left-radius: 5px;
        border-top-right-radius: 5px;
      }
    }

    p {
      width: 100%;
      height: 42px;
      padding-left: 5px;
      padding-right: 5px;
      word-break: normal;
      white-space: pre-wrap;
      word-wrap: break-word;
      text-align: left;
      font: {
        size: 14px;
        family: MicrosoftYaHei;
        weight: 400;
      }
      color: rgb(20, 20, 20);
      line-height: 18px;
      //letter-spacing: 1px;
      cursor: pointer;
    }
  }
}
</style>
