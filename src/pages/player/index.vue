<template>
  <div class="player-page">
    <div class="header">
      <navbar
        :scroll="false"
        :style_shade="false"
        :menu_v="false"
        :extend="false"
        :activeitem="activeitem"
      ></navbar>
      <div class="play-area" v-if="isReload">
        <div class="play-player">
          <video-player
            class="video-player-box vjs-custom-skin"
            ref="videoPlayer"
            :options="playerOptions"
            @ready="playerReadied"
          ></video-player>
          <!--<video-->
            <!--class="video-player-box vjs-custom-skin"-->
            <!--ref="videoPlayer"-->
            <!--:options="playerOptions"-->
            <!--@ready="playerReadied"-->
          <!--&gt;</video>-->


        </div>
        <div class="play-info">
          <el-row>
            <el-col :span="12">
              <div class="play-details">
                <div class="play-title">
                  <p ref="playTitle">{{title}}</p>
                </div>
                <!--<div class="play-append">-->
                  <!--<div class="play-share">-->
                    <!--<span>分享：</span>-->
                    <!--<a>-->
                      <!--<img alt="wechat" src="../../assets/wechat.png">-->
                    <!--</a>-->
                    <!--<a>-->
                      <!--<img alt="sina" src="../../assets/weibo.png">-->
                    <!--</a>-->
                  <!--</div>-->
                  <!--<div class="play-amount">-->
                    <!--<p>-->
                      <!--浏览量：-->
                      <!--<span>{{amount}}</span>-->
                    <!--</p>-->
                  <!--</div>-->
                <!--</div>-->
              </div>
            </el-col>
            <el-col :span="12">
              <div class="play-ad" @click="googleAd()">
                <a>
                  <img alt="ad" src="../../../static/images/ad/ad.png">
                </a>
              </div>
            </el-col>
          </el-row>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="left"></div>
      <div class="right"></div>
      <div class="main">
        <el-row>
          <el-col :span="18">
            <discuss></discuss>
          </el-col>
          <!--<el-col :span="6">-->
            <!--<recommend :data="rcData" @changeVideoData="changeVideoData"></recommend>-->
          <!--</el-col>-->
        </el-row>
      </div>
    </div>
    <div class="footer">
      <div class="line"></div>
      <footbar></footbar>
    </div>
  </div>
</template>

<script>
import "../../assets/css/custom-player.scss";
import videojs from "video.js";
window.videojs = videojs;

// hls plugin for videojs6 (replaced by VHS)
// require("videojs-contrib-hls/dist/videojs-contrib-hls.js");

export default {
  components: {},
  inject: ["reload"],
  props: {},
  data() {
    return {
      title: "",
      amount: 0,
      activeitem: ["", "", "", "", "", "", ""],
      rcData: this.$store.state.webData.RecommendedVideos.data,
      videoData: {},
      isReload: true,
      playerOptions: {
        // videojs options
        autoplay: false,
        muted: false,
        loop: false,
        preload: "auto",
        language: "en",
        playbackRates: [0.5, 1.0, 1.5, 2.0],
        aspectRatio: "16:9",
        fluid: true,
        sources: [],
        flash: { hls: { withCredentials: false } },
        html5: { hls: { withCredentials: false } },
        poster: "",
        notSupportedMessage: "遇到问题，视频无法播放",
        controlBar: {
          timeDivider: true,
          durationDisplay: true,
          remainingTimeDisplay: false,
          fullScreenToggle: true
        }
      }
    };
  },
  created() {},
  mounted() {
    this.videoData = this.$route.query.data;
    console.log(this.videoData);
    if (this.videoData == {}) {
      this.videoData = JSON.parse(localStorage.getItem("shotcut_videoData"));
    } else {
      localStorage.setItem("shotcut_videoData", JSON.stringify(this.videoData));
    }
    this.title = this.videoData.title;
    // if (this.title.length > 12) {
    //   this.title = this.title.slice(0, 12) + "...";
    // }
    this.amount = this.videoData.amount;
    this.playerOptions.poster = this.videoData.poster;
    this.playerOptions.sources = this.videoData.source;
    this.playerOptions.sources.src = require(this.videoData.source.src);

    //console.log("this is current player instance object", this.player);
    //console.log(this.rcData);
  },
  beforeDestroy() {},
  destroyed() {},
  computed: {
    player() {
      return this.$refs.videoPlayer.player;
    }
  },
  methods: {
    playerReadied(player) {
      if (this.videoData.source.type == "application/x-mpegURL") {
        let hls = player.tech({ IWillNotUseThisInPlugins: true }).hls;
        player.tech_.hls.xhr.beforeRequest = function(options) {
          // console.log(options)
          return options;
        };
      }
    },
    googleAd() {
      window.open(
        "https://www.google.com/adsense/start/#/?modal_active=none",
        "_blank"
      );
    },
    changeVideoData(recommendData) {
      this.videoData = recommendData;
      localStorage.setItem("shotcut_videoData", JSON.stringify(this.videoData));
      //console.log(this.videoData);

      this.isReload = false;

      this.$nextTick(() => {
        this.title = this.videoData.title;
        this.amount = this.videoData.amount;
        this.playerOptions.poster = this.videoData.poster;
        this.playerOptions.sources = this.videoData.source;
        this.isReload = true;
      });
    },
    changeTitleWidth(e) {}
  },
  watch: {}
};
</script>

<style lang="scss" scoped>
@import "./index";
</style>
