<template>
  <div class="home-header" v-bind:style="{height: reactiveHeight + 'px'}">
    <navbar :scroll="scroll" :style_shade="style_shade" :activeitem="activeitem"></navbar>
    <el-carousel
      :autoplay="false"
      arrow="never"
      indicator-position="none"
      ref="carousel"
      :height="reactiveHeight+'px'"
    >
      <el-carousel-item v-for="item in items" :key="item.id">
        <div class="cover">
          <img alt="bg" :src="item.poster" @click="linkToPlayer(item)">
        </div>
      </el-carousel-item>
    </el-carousel>
    <!--<div-->
      <!--class="newslist"-->
      <!--id="newslist"-->
      <!--v-bind:style="{height:reactiveHeight*0.8+'px',width:reactiveWidth*0.3+'px',top:90*(reactiveHeight/600)+'px'}"-->
    <!--&gt;-->
      <!--<ul>-->
        <!--<li-->
          <!--v-bind:class="{'list-active':items[0].actived}"-->
          <!--@mouseover="pauseCounter(0)"-->
          <!--@mouseout="recoverCounter(0)"-->
          <!--@click="linkToPlayer(items[0])"-->
        <!--&gt;-->
          <!--<a>-->
            <!--<span v-bind:class="{'span-active':items[0].actived}">{{items[0].title}}</span>-->
          <!--</a>-->
        <!--</li>-->
        <!--<li-->
          <!--v-bind:class="{'list-active':items[1].actived}"-->
          <!--@mouseover="pauseCounter(1)"-->
          <!--@mouseout="recoverCounter(1)"-->
          <!--@click="linkToPlayer(items[1])"-->
        <!--&gt;-->
          <!--<a>-->
            <!--<span v-bind:class="{'span-active':items[1].actived}">{{items[1].title}}</span>-->
          <!--</a>-->
        <!--</li>-->
        <!--<li-->
          <!--v-bind:class="{'list-active':items[2].actived}"-->
          <!--@mouseover="pauseCounter(2)"-->
          <!--@mouseout="recoverCounter(2)"-->
          <!--@click="linkToPlayer(items[2])"-->
        <!--&gt;-->
          <!--<a>-->
            <!--<span v-bind:class="{'span-active':items[2].actived}">{{items[2].title}}</span>-->
          <!--</a>-->
        <!--</li>-->
        <!--<li-->
          <!--v-bind:class="{'list-active':items[3].actived}"-->
          <!--@mouseover="pauseCounter(3)"-->
          <!--@mouseout="recoverCounter(3)"-->
          <!--@click="linkToPlayer(items[3])"-->
        <!--&gt;-->
          <!--<a>-->
            <!--<span v-bind:class="{'span-active':items[3].actived}">{{items[3].title}}</span>-->
          <!--</a>-->
        <!--</li>-->
        <!--<li-->
          <!--v-bind:class="{'list-active':items[4].actived}"-->
          <!--@mouseover="pauseCounter(4)"-->
          <!--@mouseout="recoverCounter(4)"-->
          <!--@click="linkToPlayer(items[4])"-->
        <!--&gt;-->
          <!--<a>-->
            <!--<span v-bind:class="{'span-active':items[4].actived}">{{items[4].title}}</span>-->
          <!--</a>-->
        <!--</li>-->
        <!--<li-->
          <!--v-bind:class="{'list-active':items[5].actived}"-->
          <!--@mouseover="pauseCounter(5)"-->
          <!--@mouseout="recoverCounter(5)"-->
          <!--@click="linkToPlayer(items[5])"-->
        <!--&gt;-->
          <!--<a>-->
            <!--<span v-bind:class="{'span-active':items[5].actived}">{{items[5].title}}</span>-->
          <!--</a>-->
        <!--</li>-->
        <!--<li-->
          <!--v-bind:class="{'list-active':items[6].actived}"-->
          <!--@mouseover="pauseCounter(6)"-->
          <!--@mouseout="recoverCounter(6)"-->
          <!--@click="linkToPlayer(items[6])"-->
        <!--&gt;-->
          <!--<a>-->
            <!--<span v-bind:class="{'span-active':items[6].actived}">{{items[6].title}}</span>-->
          <!--</a>-->
        <!--</li>-->
      <!--</ul>-->
    <!--</div>-->
  </div>
</template>

<script>
function todo(func, delay) {
  let timer = null;
  return function() {
    let _this = this;
    let argsArray = arguments;

    clearTimeout(timer);

    timer = (() => {
      func.apply(_this, argsArray);
    },
    delay);
  };
}

export default {
  name: "homeheader",
  props: {
    scroll: Boolean,
    style_shade: Boolean,
    activeitem: Array,
    data: Array,
    actived: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      counter: 0,
      timer: null,
      items: this.data,
      reactiveWidth: 0,
      reactiveHeight: 0
    };
  },
  created() {
    //console.log(this.data);
    this.items.forEach(item => {
      this.$set(item, "actived", false);
    });
    this.counter = 0;
    this.items[this.counter].actived = true;
    this.counter++;

    this.timer = setInterval(() => {
      if (this.counter > 6) this.counter = 0;

      if (this.counter != 0) this.items[this.counter - 1].actived = false;
      else this.items[6].actived = false;

      this.items[this.counter].actived = true;
      this.$refs.carousel.setActiveItem(this.counter);
      this.counter++;
    }, 3000);
    this.$once("hook:beforeDestroy", () => {
      clearInterval(this.timer);
      this.timer = null;
    });
  },
  mounted() {
    this.reactiveElement();

    window.addEventListener("resize", this.reactiveElement);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.reactiveElement);
  },
  destroyed() {
    console.log(window);
  },
  computed: {},
  methods: {
    reactiveElement() {
      if (document.body.clientWidth >= 1050) {
        this.reactiveWidth = document.body.clientWidth;
        this.reactiveHeight = (document.body.clientWidth / 1920) * 600;
      } else {
        // this.reactiveWidth = 1050;
        // this.reactiveHeight = (1050 / 1920) * 600;
        this.reactiveHeight = 270;
      }
      console.log(this.reactiveWidth + "-" + this.reactiveHeight);
    },
    pauseCounter(param) {
      let self = this;
      this.$nextTick(() => {
        clearInterval(this.timer);
        this.items.forEach(item => {
          self.$set(item, "actived", false);
        });
        this.items[param].actived = true;
        this.$refs.carousel.setActiveItem(param);
      });
    },
    recoverCounter(param) {
      this.counter = param;
      this.timer = setInterval(() => {
        if (this.counter == 7) this.counter = 0;

        if (this.counter != 0) this.items[this.counter - 1].actived = false;
        else this.items[6].actived = false;

        this.items[this.counter].actived = true;
        this.$refs.carousel.setActiveItem(this.counter);
        this.counter++;
      }, 3000);
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
            src: obj.video_url
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


<style lang="scss">
.list-active {
  width: 100% !important;
  height: 18% !important;
  display: flex;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.7);
  opacity: 1;
  z-index: 5;
}

.span-active {
  font-size: 20px !important;
  font-family: MicrosoftYaHei-Bold !important;
  font-weight: bold !important;
  color: rgba(255, 85, 0, 0.9) !important;
}

.home-header {
  width: 100%;
  height: 800px;
  //position: relative;

  .navbar {
    position: fixed;
    top: 0;
    z-index: 3;
  }

  .el-carousel {
    width: 100%;
    /*min-width: 1050px;*/
    position: absolute;
    top: 0;
    z-index: 1;
    cursor: pointer;

    .el-carousel__container {
      width: 100%;
      height: 100%;

      .el-carousel__item {
        width: 100%;
        height: 100%;
        margin: 0;

        .cover {
          width: 100%;
          height: 100%;
          overflow: hidden;
          position: relative;

          &:after {
            position: absolute;
            content: "";
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            box-shadow: 0 0 50px 30px rgba(0, 0, 0, 0.4) inset;
          }

          img {
            width: 100%;
            height: 100%;
          }
        }
      }
    }
  }

  .newslist {
    //width: 420px;
    //width: 40%;
    //height: 448px;
    min-width: 360px;
    position: fixed;
    right: 0;
    z-index: 2;
    background-color: rgba(0, 0, 0, 0.6);
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
    z-index: 4;

    ul {
      width: 100%;
      min-width: 360px;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: left;

      li {
        width: 100%;
        height: 12%;
        display: flex;
        align-items: center;
        transition: height 0.5s;
        cursor: pointer;

        a {
          span {
            margin-left: 24px;
            font-size: 16px;
            font-family: MicrosoftYaHei;
            font-weight: 400;
            line-height: 10px;
            color: rgba(153, 153, 153, 1);
          }
        }
      }
    }
  }
}
</style>
