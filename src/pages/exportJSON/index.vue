<template>
  <div>
    <p>数据导出 JSON</p>
    <el-button @click="exportJSON()">export</el-button>
  </div>
</template>

<script>
import { saveAs } from "file-saver";

export default {
  data() {
    return {
      webData: {
        background: {
          id: 1,
          name: "slideshow",
          title: "",
          data: [
            // {
            //   id: 1,
            //   title: "21你是鱼刺",
            //   poster: "../../../static/images/bg/bg_1.jpg",
            //   type: "video/mp4",
            //   video_url:
            //     "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/a4264544e2bbf67bb43e46f44fcad517.mp4",
            //   amount: 1
            // },
            // {
            //   id: 2,
            //   title: "达摩金黄皮肤教学",
            //   poster: "../../../static/images/bg/bg_2.jpg",
            //   type: "video/mp4",
            //   video_url:
            //     "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/aec19a6d57c35ce9d604e9577df61df8.mp4",
            //   amount: 1
            // },
            // {
            //   id: 3,
            //   title: "玛丽小酥",
            //   poster: "../../../static/images/bg/bg_3.jpg",
            //   type: "video/mp4",
            //   video_url:
            //     "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/836c100ee855a8e6cc333f0b6b8f046b.mp4",
            //   amount: 1
            // },
            // {
            //   id: 4,
            //   title: "明星拍照姿势",
            //   poster: "../../../static/images/bg/bg_4.jpg",
            //   type: "video/mp4",
            //   video_url:
            //     "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/0a8eccd7d3e1a38fa9c1547a270bab8f.mp4",
            //   amount: 1
            // },
            // {
            //   id: 5,
            //   title: "男生们 跟你称兄道弟的女生 你可要注意了！",
            //   poster: "../../../static/images/bg/bg_5.jpg",
            //   type: "video/mp4",
            //   video_url:
            //     "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/b0f694479684f2810d5bc9ef32537328.mp4",
            //   amount: 1
            // },
            // {
            //   id: 6,
            //   title: "特效师嘟拉舞",
            //   poster: "../../../static/images/bg/bg_6.jpg",
            //   type: "video/mp4",
            //   video_url:
            //     "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/ff6240b9971a0db06fe6240203949f70.mp4",
            //   amount: 1
            // },
            // {
            //   id: 7,
            //   title: "最强国产跑鞋匹克阿莉塔测评",
            //   poster: "../../../static/images/bg/bg_7.jpg",
            //   type: "video/mp4",
            //   video_url:
            //     "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/b841edd2e6a7d38a66f3b050e177b8d8.mp4",
            //   amount: 1
            // }
          ]
        },
        home: {},
        hithot: {
          tags_data: [
            {
              id: 1,
              name: " 美食",
              title: "Nini的厨房",
              isMulti: false,
              data: [
                {
                  id: 1,
                  title: " 自我介绍",
                  poster: "../../../static/images/module/6/nini_1.jpg",
                  type: "video/mp4",
                  video_url:
                    "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/284019171f328ce78a0eb975b95954ca.mp4",
                  amount: 3824
                }
              ]
            },
            {
              id: 2,
              name: "游戏",
              title: "讲道视频",
              isMulti: false,
              data: [
                {
                  id: 1,
                  title: "80锤",
                  poster: "../../../static/images/module/3/pipi_1.png",
                  type: "video/mp4",
                  video_url:
                    "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/6a23d04068bdb7183250b6897a94e562.mp4",
                  amount: 3824
                }
              ]
            },
            {
              id: 3,
              name: "时尚",
              title: "",
              isMulti: true,
              data: [
                {
                  id: 1,
                  name: "shipinlanmu1",
                  title: "斯内克杨",
                  data: [
                    {
                      id: 1,
                      title: "AIR MAX DAY_ Moment",
                      poster: "../../../static/images/module/1/snky_1.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/7ef2b7297243a1380673314b21e892d8.m3u8",
                      amount: 3824
                    },
                    {
                      id: 2,
                      title: "aj 实战鞋",
                      poster: "../../../static/images/module/1/snky_2.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/1536ee924bb48a1e48c549eee7f3c3ff.m3u8",
                      amount: 4928
                    },
                    {
                      id: 3,
                      title: "aj打球",
                      poster: "../../../static/images/module/1/snky_3.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/23d01c254c87e634127c2f0565097367.m3u8",
                      amount: 2938
                    }
                  ]
                },
                {
                  id: 2,
                  name: "shipinlanmu2",
                  title: "美人秀秀",
                  data: [
                    {
                      id: 1,
                      title: "紫色印度小哥哥",
                      poster: "../../../static/images/module/4/mrxx_1.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/74c9cd178b1260613f931cb3fa030ff7.m3u8",
                      amount: 32525
                    },
                    {
                      id: 2,
                      title: "甜美文艺风",
                      poster: "../../../static/images/module/4/mrxx_2.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/f41e231b07b605babf6f8f876d3706ef.m3u8",
                      amount: 4325
                    },
                    {
                      id: 3,
                      title: "牛仔外套小姐姐",
                      poster: "../../../static/images/module/4/mrxx_3.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/d7db4a58ddf3116bb1388c22072e1ac8.m3u8",
                      amount: 95363
                    }
                  ]
                },
                {
                  id: 3,
                  name: "shipinlanmu3",
                  title: "青年风采",
                  data: [
                    {
                      id: 1,
                      title: "变废为宝的美妆工具",
                      poster: "../../../static/images/module/2/vivi_1.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/ea270c3c10dd57153ac0aaf8a8a4f2ab.m3u8",
                      amount: 3824
                    },
                    {
                      id: 2,
                      title: "超减龄心机腮红",
                      poster: "../../../static/images/module/2/vivi_2.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/23247978715c1e26339d5dfb8451817b.m3u8",
                      amount: 4928
                    },
                    {
                      id: 3,
                      title: "超强干货！芒果后台化妆步骤",
                      poster: "../../../static/images/module/2/vivi_3.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/de81e6a6517c3869b05fafda2fdb41fb.m3u8",
                      amount: 2938
                    }
                  ]
                }
              ]
            },
            {
              id: 4,
              name: "旅游",
              title: "旅游尹淘小玩子",
              isMulti: false,
              data: [
                {
                  id: 1,
                  title: "ck小镇第一条",
                  poster: "../../../static/images/module/5/lvwz_1.jpg",
                  type: "video/mp4",
                  video_url:
                    "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/7be00d94032db6d8499dae531bc33394.mp4",
                  amount: 3824
                }
              ]
            },
            {
              id: 5,
              name: "搞笑",
              title: "冷笑话",
              isMulti: false,
              data: [
                {
                  id: 1,
                  title: "冷笑话-1",
                  poster: "../../../static/images/module/7/lxy_1.jpg",
                  type: "application/x-mpegURL",
                  video_url: "",
                  amount: 3824
                }
              ]
            },
            {
              id: 6,
              name: "情感",
              title: "",
              isMulti: true,
              data: [
                {
                  id: 1,
                  name: "",
                  title: "晏炜观点秀",
                  data: [
                    {
                      id: 1,
                      title: "什么样的人总是被人挑刺",
                      poster: "../../../static/images/module/8/gdx_1.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/d5596d4afa0f7bfeac168ecc41674c60.m3u8",
                      amount: 3824
                    },
                    {
                      id: 2,
                      title: "轻易承诺",
                      poster: "../../../static/images/module/8/gdx_2.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/01d15ef8c49deb3a7ce029622f70adc0.m3u8",
                      amount: 4928
                    },
                    {
                      id: 3,
                      title: "不懂感恩没朋友",
                      poster: "../../../static/images/module/8/gdx_3.jpg",
                      type: "application/x-mpegURL",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/f9adb73b2d769581509eb73d9d0d2c9e.m3u8",
                      amount: 2938
                    }
                  ]
                },
                {
                  id: 2,
                  name: "",
                  title: "玛丽小酥",
                  data: [
                    {
                      id: 1,
                      title: "带妹高手 第1话",
                      poster: "../../../static/images/module/9/mlxs_1.jpg",
                      type: "video/mp4",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/35652b3879534d41320a1282c7a20fed.mp4",
                      amount: 833
                    },
                    {
                      id: 2,
                      title: "带妹高手 第2话",
                      poster: "../../../static/images/module/9/mlxs_2.jpg",
                      type: "video/mp4",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/4c3a18b9cb97f3bdc3d7efc676960133.mp4",
                      amount: 3414
                    },
                    {
                      id: 3,
                      title: "带妹高手 第3话",
                      poster: "../../../static/images/module/9/mlxs_3.jpg",
                      type: "video/mp4",
                      video_url:
                        "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/753914f31cf9566f12626bcadb35ae37.mp4",
                      amount: 2616
                    }
                  ]
                }
              ]
            },
            {
              id: 7,
              name: "特效",
              title: "生命见证",
              isMulti: false,
              data: [
                {
                  id: 1,
                  title: "迦南见证detail",
                  poster: "../../../static/original/chen.jpg",
                  type: "application/x-mpegURL",
                  video_url:
                    "../../../static/original/chen.mp4",
                  amount: 3824
                }
              ]
            },
            {
              id: 8,
              name: "生活",
              title: "短秀新生活",
              isMulti: false,
              data: [
                {
                  id: 1,
                  title: "冰棒棍玩出新花样",
                  poster: "",
                  type: "application/x-mpegURL",
                  video_url:
                    "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/5aa4bd83a0b06431854d36ff589e5543.m3u8",
                  amount: 3824
                }
              ]
            }
          ],
          content_data: []
        },
        monthly_rank: {
          module_data_1: [
            {
              id: 1,
              title: "1",
              poster: "../../../static/images/monthly_rank/1/hot_1.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 2,
              title: "2",
              poster: "../../../static/images/monthly_rank/1/hot_2.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 3,
              title: "3",
              poster: "../../../static/images/monthly_rank/1/hot_3.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 4,
              title: "4",
              poster: "../../../static/images/monthly_rank/1/hot_4.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 5,
              title: "5",
              poster: "../../../static/images/monthly_rank/1/hot_5.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 6,
              title: "6",
              poster: "../../../static/images/monthly_rank/1/hot_6.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 7,
              title: "7",
              poster: "../../../static/images/monthly_rank/1/hot_7.png",
              type: "",
              video_url: "",
              amount: 0
            }
          ],
          module_data_2: [
            {
              id: 1,
              title: "1",
              poster: "../../../static/images/monthly_rank/2/hot_rc_1.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 2,
              title: "2",
              poster: "../../../static/images/monthly_rank/2/hot_rc_2.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 3,
              title: "3",
              poster: "../../../static/images/monthly_rank/2/hot_rc_3.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 4,
              title: "4",
              poster: "../../../static/images/monthly_rank/2/hot_rc_4.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 5,
              title: "5",
              poster: "../../../static/images/monthly_rank/2/hot_rc_5.png",
              type: "",
              video_url: "",
              amount: 0
            },
            {
              id: 6,
              title: "6",
              poster: "../../../static/images/monthly_rank/2/hot_rc_6.png",
              type: "",
              video_url: "",
              amount: 0
            }
          ]
        },
        heat_fashion: {},
        best_punchline: {},
        youth_playlet: {},
        module_data_1: {
          id: 2,
          name: "shipinlanmu",
          title: "斯内克杨",
          data: [
            {
              id: 1,
              title: "AIR MAX DAY_ Moment",
              poster: "../../../static/images/module/1/snky_1.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/7ef2b7297243a1380673314b21e892d8.m3u8",
              amount: 3824
            },
            {
              id: 2,
              title: "aj 实战鞋",
              poster: "../../../static/images/module/1/snky_2.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/1536ee924bb48a1e48c549eee7f3c3ff.m3u8",
              amount: 4928
            },
            {
              id: 3,
              title: "aj打球",
              poster: "../../../static/images/module/1/snky_3.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/23d01c254c87e634127c2f0565097367.m3u8",
              amount: 2938
            },
            {
              id: 4,
              title: "灌篮高手赤木刚宪最终版",
              poster: "../../../static/images/module/1/snky_4.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/ef63181459025cf0d7850b189d529211.m3u8",
              amount: 2742
            },
            {
              id: 5,
              title: "灌篮高手宫城良田最终版",
              poster: "../../../static/images/module/1/snky_5.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/d6884c9d2fb07444aa0ced95cfd94a14.m3u8",
              amount: 3824
            },
            {
              id: 6,
              title: "灌篮高手流川枫最终版",
              poster: "../../../static/images/module/1/snky_6.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/ff2ad291486a67d056e8835ee1f377ef.m3u8",
              amount: 4928
            },
            {
              id: 7,
              title: "灌篮高手三井寿最终版",
              poster: "../../../static/images/module/1/snky_7.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/9b3a2d246ae2e3bb6ee5ccf0e2e586a9.m3u8",
              amount: 2938
            },
            {
              id: 8,
              title: "灌篮高手樱木花道最终版",
              poster: "../../../static/images/module/1/snky_8.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/d9f35ae0d1fc111fa385852b8283e04c.m3u8",
              amount: 2742
            },
            {
              id: 9,
              title: "价格低颜值起飞",
              poster: "../../../static/images/module/1/snky_9.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/11ef87f1de63d483bb9ca0cf01735332.m3u8",
              amount: 3824
            },
            {
              id: 10,
              title: "价格起飞的球鞋有哪些特点，知道了能省不少",
              poster: "../../../static/images/module/1/snky_10.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/60c1b7452ad89a0c9cd0ba6cfcfe1018.m3u8",
              amount: 4928
            },
            {
              id: 11,
              title: "欧文上改",
              poster: "../../../static/images/module/1/snky_11.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/527a1f1c43fb04452213afd87c62b041.m3u8",
              amount: 2938
            },
            {
              id: 12,
              title: "欧文下改",
              poster: "../../../static/images/module/1/snky_12.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/8a4338cef8cd5302b4ccb5b9dc8bb218.m3u8",
              amount: 2742
            },
            {
              id: 13,
              title: "勤工俭学",
              poster: "../../../static/images/module/1/snky_13.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/a1b9066a80de6f87be72ba21693861eb.m3u8",
              amount: 4928
            },
            {
              id: 14,
              title: "球鞋恋爱",
              poster: "../../../static/images/module/1/snky_14.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/8f49f35e9e9277b131bfaeb0899ff5dd.m3u8",
              amount: 2938
            }

          ]
        },
        module_data_2: {
          id: 3,
          name: "shipinlanmu2",
          title: "青年风采",
          data: [
            {
              id: 1,
              title: "变废为宝的美妆工具",
              poster: "../../../static/images/module/2/vivi_1.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/ea270c3c10dd57153ac0aaf8a8a4f2ab.m3u8",
              amount: 3824
            },
            {
              id: 2,
              title: "超减龄心机腮红",
              poster: "../../../static/images/module/2/vivi_2.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/23247978715c1e26339d5dfb8451817b.m3u8",
              amount: 4928
            },
            {
              id: 3,
              title: "超强干货！芒果后台化妆步骤",
              poster: "../../../static/images/module/2/vivi_3.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/de81e6a6517c3869b05fafda2fdb41fb.m3u8",
              amount: 2938
            },
            {
              id: 4,
              title: "初一到初七发型",
              poster: "../../../static/images/module/2/vivi_4.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/c8382542783f3c87373fa038c24a9e4f.m3u8",
              amount: 2742
            },
            {
              id: 5,
              title: "唇形不完美，口红来补救",
              poster: "../../../static/images/module/2/vivi_5.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/80f0fa0d837c0a6b02dbe34d0d90ddc7.m3u8",
              amount: 3824
            },
            {
              id: 6,
              title: "倒贴的爱情要不要坚持",
              poster: "../../../static/images/module/2/vivi_6.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/62f83d1e827932d67be3faa8e2ec3059.m3u8",
              amount: 4928
            },
            {
              id: 7,
              title: "抖音-男友大改造25秒",
              poster: "../../../static/images/module/2/vivi_7.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/7529fde3464450c6e078be1ca454af82.m3u8",
              amount: 2938
            },
            {
              id: 8,
              title: "发财丸子头",
              poster: "../../../static/images/module/2/vivi_8.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/bea0cf61ca8eb1467afc3d26e0a10e1f.m3u8",
              amount: 2742
            },
            {
              id: 9,
              title: "高圆圆最爱的军绿色",
              poster: "../../../static/images/module/2/vivi_9.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/8707bc44621608524fc5b60e6f2073d6.m3u8",
              amount: 3824
            },
            {
              id: 10,
              title: "化妆前的你vs化妆后的你",
              poster: "../../../static/images/module/2/vivi_10.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/79dd38751d1457f11223f2a4cf6a8089.m3u8",
              amount: 4928
            },
            {
              id: 11,
              title: "红毯底妆画法",
              poster: "../../../static/images/module/2/vivi_11.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/3fec0a62421bab07eab926d38b49dc2c.m3u8",
              amount: 2938
            },
            {
              id: 12,
              title: "会喷香水的姑娘，灵魂自带香气",
              poster: "../../../static/images/module/2/vivi_12.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/4e3fde170746b6fb2a8ceebfba232c8d.m3u8",
              amount: 4928
            },
            {
              id: 13,
              title: "鉴表特别篇-男友会鉴",
              poster: "../../../static/images/module/2/vivi_13.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/66a05e07b355ea62a903bf84634868d5.m3u8",
              amount: 2938
            },
            {
              id: 14,
              title: "鉴渣之男友习惯性打压我",
              poster: "../../../static/images/module/2/vivi_14.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/cf3d4bf407dcc35e395c23b36cf7f9ff.m3u8",
              amount: 2742
            }

          ]
        },
        module_data_3: {
          id: 4,
          name: "shipinlanmu3",
          title: "圣经",
          data: [
            {
              id: 1,
              title: "80锤",
              poster: "../../../static/images/module/3/pipi_1.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/6a23d04068bdb7183250b6897a94e562.mp4",
              amount: 3824
            },
            {
              id: 2,
              title: "ad嬴政教学",
              poster: "../../../static/images/module/3/pipi_2.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/44727ce99db296bc86c60cee1f3a00e0.mp4",
              amount: 4928
            },
            {
              id: 3,
              title: "P图2甄家系列",
              poster: "../../../static/images/module/3/pipi_3.png",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/85fffb771cbf73f35e2fbb3854293c4a.m3u8",
              amount: 2938
            },
            {
              id: 4,
              title: "p图君",
              poster: "../../../static/images/module/3/pipi_4.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/966da4a0095e2b22b0c28d27ff1f8c8c.mp4",
              amount: 2742
            },
            {
              id: 5,
              title: "百穿铭文",
              poster: "../../../static/images/module/3/pipi_5.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/8e969f254f522f31dafeef0468e4a6ff.mp4",
              amount: 3824
            },
            {
              id: 6,
              title: "打野鱼",
              poster: "../../../static/images/module/3/pipi_6.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/16c6183f7968f73f3081d6c74c4ea506.mp4",
              amount: 4928
            },
            {
              id: 7,
              title: "大人物鲁班被迫杀人",
              poster: "../../../static/images/module/3/pipi_7.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/cd2b54c371ef3d9a35af82f023cba506.mp4",
              amount: 2938
            },
            {
              id: 8,
              title: "狄仁杰教学",
              poster: "../../../static/images/module/3/pipi_8.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/aec1ec01e084d920f7957a2b85effe86.mp4",
              amount: 2742
            },
            {
              id: 9,
              title: "怼儿慢放444",
              poster: "../../../static/images/module/3/pipi_9.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/5714828b5cfee6ff9857938f7bd11918.mp4",
              amount: 3824
            },
            {
              id: 10,
              title: "法师铭文",
              poster: "../../../static/images/module/3/pipi_10.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/50b450a1e79559d1df6b2d4b9b9807af.mp4",
              amount: 4928
            },
            {
              id: 11,
              title: "隔壁老王",
              poster: "../../../static/images/module/3/pipi_11.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/24f40dd470fe0c34cad83f1cf7d785e4.mp4",
              amount: 2938
            },
            {
              id: 12,
              title: "宫本教学",
              poster: "../../../static/images/module/3/pipi_12.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/2ece9dc5229f7c816d1046ab427d4eeb.mp4",
              amount: 4928
            },
            {
              id: 13,
              title: "鬼畜02雅典娜专场",
              poster: "../../../static/images/module/3/pipi_13.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/c20882e186a4fbcde3e837b6d32b6dc6.mp4",
              amount: 2938
            },
            {
              id: 14,
              title: "猴捶鲁班",
              poster: "../../../static/images/module/3/pipi_14.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/cbe6c82684f6862c6a0dfc2535947817.mp4",
              amount: 2742
            }

          ]
        },
        module_data_4: {
          id: 5,
          name: "",
          title: "冷笑话",
          data: [
            {
              id: 1,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_1.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 2,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_2.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 3,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_3.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 4,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_4.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 5,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_5.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 6,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_6.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 7,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_7.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 8,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_8.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 9,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_9.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 10,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_10.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 11,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_11.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 12,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_12.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 13,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_13.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 14,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_14.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            }

          ]
        },
        module_data_5: {
          id: 6,
          name: "",
          title: "其他内容",
          data: [
            {
              id: 1,
              title: "带妹高手 第1话",
              poster: "../../../static/images/module/9/mlxs_1.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/35652b3879534d41320a1282c7a20fed.mp4",
              amount: 833
            },
            {
              id: 2,
              title: "带妹高手 第2话",
              poster: "../../../static/images/module/9/mlxs_2.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/4c3a18b9cb97f3bdc3d7efc676960133.mp4",
              amount: 3414
            },
            {
              id: 3,
              title: "带妹高手 第3话",
              poster: "../../../static/images/module/9/mlxs_3.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/753914f31cf9566f12626bcadb35ae37.mp4",
              amount: 2616
            },
            {
              id: 4,
              title: "带妹高手 第4话",
              poster: "../../../static/images/module/9/mlxs_4.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/fa39e2492c0a7d6bec7caf625ed606d6.m3u8",
              amount: 2616
            },
            {
              id: 5,
              title: "霸道男友如何相处",
              poster: "../../../static/images/module/9/mlxs_5.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/2262d098a1ff14d43b324417779dd678.mp4",
              amount: 2616
            },
            {
              id: 6,
              title: "比悲伤更悲伤的故事定",
              poster: "../../../static/images/module/9/mlxs_6.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/be40145b7e72cbb6e1d8fe7c92ca13c8.m3u8",
              amount: 2616
            },
            {
              id: 7,
              title: "分手后还能做朋友吗",
              poster: "../../../static/images/module/9/mlxs_7.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/a4c8fafddc8e04340240e47b11cb1134.m3u8",
              amount: 2616
            },
            {
              id: 8,
              title: "猫系男友如何相处",
              poster: "../../../static/images/module/9/mlxs_8.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/ebe3579e0c0c0f58812903ca67c120d4.mp4",
              amount: 2616
            },
            {
              id: 9,
              title: "男生喜欢你的四个表现",
              poster: "../../../static/images/module/9/mlxs_9.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/f66982b540cd482a14aac0b6f68f04e2.mp4",
              amount: 2616
            },
            {
              id: 10,
              title: "喜欢你的人爱意是藏不住的",
              poster: "../../../static/images/module/9/mlxs_10.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/2bd1e9e36c04854529b92d50f6f611fc.m3u8",
              amount: 2616
            },
            {
              id: 11,
              title: "尖叫吧！小酥1",
              poster: "../../../static/images/module/9/mlxs_11.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/b4379077d2c11615de978805903eeb94.mp4",
              amount: 2616
            },
            {
              id: 12,
              title: "尖叫吧！小酥2",
              poster: "../../../static/images/module/9/mlxs_12.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/8adfb9a5b4fdb8aa08c25a52dbefb501.mp4",
              amount: 2616
            },
            {
              id: 13,
              title: "尖叫吧！小酥3",
              poster: "../../../static/images/module/9/mlxs_13.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/6128bb689bfd1b5dcc5e58f11bd4eb49.mp4",
              amount: 2616
            },
            {
              id: 14,
              title: "尖叫吧！小酥4",
              poster: "../../../static/images/module/9/mlxs_14.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/f93e517ffae75e1ebc8c4745cd448513.m3u8",
              amount: 2616
            }

          ]
        },
        module_data_6: {},
        module_data_7: {},
        module_data_8: {},
        module_data_9: {},
        module_data_10: {
          id: 11,
          name: "",
          title: "生命见证",
          data: [
            {
              id: 1,
              title: "变大变小",
              poster: "../../../static/images/module/10/fktx_1.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/60b7a93c08a529e33be68cc07b5f29af.m3u8",
              amount: 3824
            },
            {
              id: 2,
              title: "彩虹豆跳舞",
              poster: "../../../static/images/module/10/fktx_2.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/418687347c556a07f7fe2b0365da80c6.m3u8",
              amount: 4928
            },
            {
              id: 3,
              title: "插队",
              poster: "../../../static/images/module/10/fktx_3.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/88ecb886c10c0aa0d97ab28786bbe1d7.m3u8",
              amount: 2938
            },
            {
              id: 4,
              title: "大黄蜂买买买",
              poster: "../../../static/images/module/10/fktx_4.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/e482d103d9bea210d46f7528e74c5e67.m3u8",
              amount: 2742
            },
            {
              id: 5,
              title: "大黄蜂汽车变形",
              poster: "../../../static/images/module/10/fktx_5.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/e5542840150002c0cb33e26fc9711c14.m3u8",
              amount: 3824
            },
            {
              id: 6,
              title: "大黄蜂水冰月跳舞",
              poster: "../../../static/images/module/10/fktx_6.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/bea7c2812118cc61f17c2866166cf2b2.m3u8",
              amount: 4928
            },
            {
              id: 7,
              title: "大楼变气球撩妹",
              poster: "../../../static/images/module/10/fktx_7.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/76e5260631fc544d8705c7aac47964d3.m3u8",
              amount: 2938
            },
            {
              id: 8,
              title: "大楼变气球撩妹·合拍版",
              poster: "../../../static/images/module/10/fktx_8.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/10c4bba84fe69c77c23731f39695bbfa.m3u8",
              amount: 2742
            },
            {
              id: 9,
              title: "懂车帝 第六版",
              poster: "../../../static/images/module/10/fktx_9.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/ece866caadc1f762d7da35815108b622.m3u8",
              amount: 3824
            },
            {
              id: 10,
              title: "嘟啦舞",
              poster: "../../../static/images/module/10/fktx_10.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/32f0fb5dcec40a564c955f865e352d96.m3u8",
              amount: 4928
            },
            {
              id: 11,
              title: "oppo手机抢车位",
              poster: "../../../static/images/module/10/fktx_11.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/2334e5fb608be0c5c4939c56462e59ba.m3u8",
              amount: 2938
            },
            {
              id: 12,
              title: "多力多滋薯片",
              poster: "../../../static/images/module/10/fktx_12.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/f199d658673b8e83c0a9d87d2f188283.m3u8",
              amount: 4928
            },
            {
              id: 13,
              title: "乐事大波浪薯片",
              poster: "../../../static/images/module/10/fktx_13.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/c7f99b40289d24d6f459e076d76ecf9e.m3u8",
              amount: 2938
            },
            {
              id: 14,
              title: "陆风汽车",
              poster: "../../../static/images/module/10/fktx_14.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/a42b4287d8ea06e88614635798d3617b.m3u8",
              amount: 2742
            }

          ]
        },
        RecommendedVideos: {
          id: 6,
          name: "slideshow",
          title: "推荐视频",
          data: [
            {
              id: 1,
              title: "全员毒奶流",
              poster: "../../../static/images/recommend/tuijian_2.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/c09ac3979c0eacff28cf1ffb146c988f.mp4",
              amount: 7362
            },
            {
              id: 2,
              title: "女友受委屈改",
              poster: "../../../static/images/recommend/tuijian_3.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/fcb451ac65c2c39d807bd286273874d7.mp4",
              amount: 4739
            },
            {
              id: 3,
              title: "大阪2",
              poster: "../../../static/images/recommend/tuijian_4.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/996d1e284a9e263c17db14f8e452ae32.mp4",
              amount: 6737
            }
          ]
        }
      }
    };
  },
  created() {},
  mounted() {},
  methods: {
    exportJSON() {
      let blob = new Blob([JSON.stringify(this.webData)], {
        type: "text/plain;charset=utf-8"
      });

      saveAs(blob, "data.json");
      alert("All Ready");
    }
  }
};
</script>
