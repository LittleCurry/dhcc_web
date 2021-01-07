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
            {
              id: 1,
              title: "21你是鱼刺",
              poster: "../../../static/images/bg/bg_1.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/a4264544e2bbf67bb43e46f44fcad517.mp4",
              amount: 1
            },
            {
              id: 2,
              title: "达摩金黄皮肤教学",
              poster: "../../../static/images/bg/bg_2.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/aec19a6d57c35ce9d604e9577df61df8.mp4",
              amount: 1
            },
            {
              id: 3,
              title: "玛丽小酥",
              poster: "../../../static/images/bg/bg_3.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/836c100ee855a8e6cc333f0b6b8f046b.mp4",
              amount: 1
            },
            {
              id: 4,
              title: "明星拍照姿势",
              poster: "../../../static/images/bg/bg_4.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/0a8eccd7d3e1a38fa9c1547a270bab8f.mp4",
              amount: 1
            },
            {
              id: 5,
              title: "男生们 跟你称兄道弟的女生 你可要注意了！",
              poster: "../../../static/images/bg/bg_5.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/b0f694479684f2810d5bc9ef32537328.mp4",
              amount: 1
            },
            {
              id: 6,
              title: "特效师嘟拉舞",
              poster: "../../../static/images/bg/bg_6.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/ff6240b9971a0db06fe6240203949f70.mp4",
              amount: 1
            },
            {
              id: 7,
              title: "最强国产跑鞋匹克阿莉塔测评",
              poster: "../../../static/images/bg/bg_7.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/b841edd2e6a7d38a66f3b050e177b8d8.mp4",
              amount: 1
            }
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
                  title: "变大变小",
                  poster: "../../../static/images/module/10/fktx_1.jpg",
                  type: "application/x-mpegURL",
                  video_url:
                    "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/60b7a93c08a529e33be68cc07b5f29af.m3u8",
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
            },
            {
              id: 15,
              title: "水泥地杀手",
              poster: "../../../static/images/module/1/snky_15.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/07cb4027784e367da59b4b1c284125e1.m3u8",
              amount: 2742
            },
            {
              id: 16,
              title: "同框买鞋子",
              poster: "../../../static/images/module/1/snky_16.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/332bbb218405959675d97d512c8957d6.m3u8",
              amount: 3824
            },
            {
              id: 17,
              title: "兔八哥",
              poster: "../../../static/images/module/1/snky_17.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/b07b9d0690d60827a62e1019eb8156a1.m3u8",
              amount: 4928
            },
            {
              id: 18,
              title: "压到脚",
              poster: "../../../static/images/module/1/snky_18.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/69a82e23681edc931ca014b6c481fd90.m3u8",
              amount: 2938
            },
            {
              id: 19,
              title: "压岁鞋",
              poster: "../../../static/images/module/1/snky_19.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/69a82e23681edc931ca014b6c481fd90.m3u8",
              amount: 2742
            },
            {
              id: 20,
              title: "一不小心就飘了，再也不在这种人面前比鞋多了",
              poster: "../../../static/images/module/1/snky_20.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/de418407de75042454f5302b7212274f.m3u8",
              amount: 3824
            },
            {
              id: 21,
              title: "支线篮球鞋",
              poster: "../../../static/images/module/1/snky_21.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/5001fa0f456425dd51d2cb8693dcd908.m3u8",
              amount: 4928
            },
            {
              id: 22,
              title: "阿丽塔改",
              poster: "../../../static/images/module/1/snky_22.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/57f7fd191bf8aa0cdcbd8690c40df604.m3u8",
              amount: 2938
            },
            {
              id: 23,
              title: "记住男朋友的鞋码 买！",
              poster: "../../../static/images/module/1/snky_23.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/cf3d69b51525848d5c9af770bb8e7ea4.m3u8",
              amount: 2742
            },
            {
              id: 24,
              title: "篮大AIR",
              poster: "../../../static/images/module/1/snky_24.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/e6bf2ceabdb6c4d12e517618209e587e.m3u8",
              amount: 3824
            },
            {
              id: 25,
              title: "聊鞋狗不懂的话题 修改",
              poster: "../../../static/images/module/1/snky_25.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/fd44166d0d0e14374e466b9c6bafbe1a.m3u8",
              amount: 4928
            },
            {
              id: 26,
              title: "路人王vlog",
              poster: "../../../static/images/module/1/snky_26.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/47bd8c3ef0d65886b0138921520bf8de.m3u8",
              amount: 2938
            },
            {
              id: 27,
              title: "马尔代夫",
              poster: "../../../static/images/module/1/snky_27.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/b196c17d50f72a67e34ff48f5010cb30.m3u8",
              amount: 2742
            },
            {
              id: 28,
              title: "送男友鞋子",
              poster: "../../../static/images/module/1/snky_28.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/9314bc08a52186f55e697328e43fddc2.m3u8",
              amount: 2742
            },
            {
              id: 29,
              title: "鞋狗尴尬",
              poster: "../../../static/images/module/1/snky_29.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/1d82e289cf6e501e09dcc5506d2d95bc.m3u8",
              amount: 3824
            },
            {
              id: 30,
              title: "鞋狗男友",
              poster: "../../../static/images/module/1/snky_30.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/f6bae73f771d196cb89c09abaccdca3e.m3u8",
              amount: 4928
            },
            {
              id: 31,
              title: "鞋码怎么选2",
              poster: "../../../static/images/module/1/snky_31.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/77a778606d4133dd595697db8e4caacb.m3u8",
              amount: 2938
            },
            {
              id: 32,
              title: "谣言",
              poster: "../../../static/images/module/1/snky_32.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/5b5d1e2d5ee2fc949fcdad11b815ae81.m3u8",
              amount: 2742
            },
            {
              id: 33,
              title: "詹姆斯1516",
              poster: "../../../static/images/module/1/snky_33.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/4cd12fcbec80763a25f7b0a657679e6a.m3u8",
              amount: 4928
            },
            {
              id: 34,
              title: "球鞋恋爱 ",
              poster: "../../../static/images/module/1/snky_34.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/7e4e02ba79fad34cd14c1978d2050093.m3u8",
              amount: 2938
            },
            {
              id: 35,
              title: "闪电侠",
              poster: "../../../static/images/module/1/snky_35.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/d0da3b911ff62ce66e267dffa855df58.m3u8",
              amount: 2742
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
            },
            {
              id: 15,
              title: "精灵妆+女王妆拼接",
              poster: "../../../static/images/module/2/vivi_15.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/7ad0dfe3487cef21abbfad823b84040f.m3u8",
              amount: 3824
            },
            {
              id: 16,
              title: "卷发棒攻略（上）",
              poster: "../../../static/images/module/2/vivi_16.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/f9b898a6c013394835e35ecdfee721a4.m3u8",
              amount: 4928
            },
            {
              id: 17,
              title: "卷发棒攻略（下）",
              poster: "../../../static/images/module/2/vivi_17.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/c19c03469e38b416ddf0842a47461437.mp4",
              amount: 2938
            },
            {
              id: 18,
              title: "绝不脱妆的眼线教程",
              poster: "../../../static/images/module/2/vivi_18.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/37cdff0e1d00a8304356bf31075e92f5.m3u8",
              amount: 2742
            },
            {
              id: 19,
              title: "明星拍照姿势",
              poster: "../../../static/images/module/2/vivi_19.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/8d34260d2e5dc715a64dfa941c39b584.m3u8",
              amount: 3824
            },
            {
              id: 20,
              title: "明星为什么爱去时装周",
              poster: "../../../static/images/module/2/vivi_20.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/fcd335b51eb91f2256b32658265311de.m3u8",
              amount: 4928
            },
            {
              id: 21,
              title: "男友异性朋友抖音",
              poster: "../../../static/images/module/2/vivi_21.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/6cc3b16c14e2cf9120c892dbfb31f667.m3u8",
              amount: 2938
            },
            {
              id: 22,
              title: "女明星的黄金3秒补水法则",
              poster: "../../../static/images/module/2/vivi_22.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/6da6300a8e1e8e5149e184442541f047.m3u8",
              amount: 3824
            },
            {
              id: 23,
              title: "女明星最怕的法令纹",
              poster: "../../../static/images/module/2/vivi_23.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/5c27aa878b696c927ad34d8701fedc14.mp4",
              amount: 4928
            },
            {
              id: 24,
              title: "三八妇女节宣言",
              poster: "../../../static/images/module/2/vivi_24.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/073c823450ef570490efa6f79a2687a5.mp4",
              amount: 2938
            },
            {
              id: 25,
              title: "三步简单卷发 打造少女心发型",
              poster: "../../../static/images/module/2/vivi_25.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/c807ccbcd415c8c15ea314fd694fc1b5.m3u8",
              amount: 2742
            },
            {
              id: 26,
              title: "生僻字",
              poster: "../../../static/images/module/2/vivi_26.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/043096586b75a6933866a08a0e55da40.m3u8",
              amount: 3824
            },
            {
              id: 27,
              title: "时尚大片抖音版",
              poster: "../../../static/images/module/2/vivi_27.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/4c5e14b5adf95017884de020dc6bd701.m3u8",
              amount: 4928
            },
            {
              id: 28,
              title: "水波纹卷发 ",
              poster: "../../../static/images/module/2/vivi_28.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/dc80d1db50c09bed0620eb8552b24b75.m3u8",
              amount: 2938
            },
            {
              id: 29,
              title: "说好的穿厚点你竟然",
              poster: "../../../static/images/module/2/vivi_29.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/dd8459f5db5d8df65b8f3fba0ee0e835.m3u8",
              amount: 4928
            },
            {
              id: 30,
              title: "心机腮红",
              poster: "../../../static/images/module/2/vivi_30.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/7cf28e5ad8279f7591534ae6610fb8da.m3u8",
              amount: 2938
            },
            {
              id: 31,
              title: "学郑秀晶臭脸拍照",
              poster: "../../../static/images/module/2/vivi_31.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/81d503ba18182d305eede095e86ec486.m3u8",
              amount: 2742
            },
            {
              id: 32,
              title: "樱花少女妆",
              poster: "../../../static/images/module/2/vivi_32.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/a315d0e45b77c2bd4eac79948eb186f0.m3u8",
              amount: 3824
            },
            {
              id: 33,
              title: "真假闺蜜之饭局",
              poster: "../../../static/images/module/2/vivi_33.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/792af0a04310a586f35830c7fb426fe9.m3u8",
              amount: 4928
            },
            {
              id: 34,
              title: "正确的护肤步骤",
              poster: "../../../static/images/module/2/vivi_34.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/dee0f520ffb3d1b3b58ab498e7dfa872.mp4",
              amount: 2938
            },
            {
              id: 35,
              title: "主持人高跟鞋",
              poster: "../../../static/images/module/2/vivi_35.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/835f7d6df78bb2a07852d299a6e0f223.mp4",
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
            },
            {
              id: 15,
              title: "猴子新皮肤教学",
              poster: "../../../static/images/module/3/pipi_15.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/5d5834bc0c3b917406bd4f35dd628ddc.mp4",
              amount: 3824
            },
            {
              id: 16,
              title: "回城飞锤",
              poster: "../../../static/images/module/3/pipi_16.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/7aa0fdf3b5b46c5fb8e556aa713a0ccc.mp4",
              amount: 4928
            },
            {
              id: 17,
              title: "橘子bug",
              poster: "../../../static/images/module/3/pipi_17.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/05642f78c662b6c03791e405de058aa6.mp4",
              amount: 2938
            },
            {
              id: 18,
              title: "铠教程",
              poster: "../../../static/images/module/3/pipi_18.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/96a3e755f5c373aff3675a389a9fe293.m3u8",
              amount: 2742
            },
            {
              id: 19,
              title: "克制嫦娥",
              poster: "../../../static/images/module/3/pipi_19.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/8ea73116800e83368a74cd0cc45e62b2.mp4",
              amount: 3824
            },
            {
              id: 20,
              title: "抠鼻子",
              poster: "../../../static/images/module/3/pipi_20.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/a253c2c259a2c73e3650d8a68e453f57.mp4",
              amount: 4928
            },
            {
              id: 21,
              title: "快速取胜",
              poster: "../../../static/images/module/3/pipi_21.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/3c847f6ff43d981cebcb8f9747a145d2.mp4",
              amount: 2938
            },
            {
              id: 22,
              title: "李信秒鲁班",
              poster: "../../../static/images/module/3/pipi_22.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/011a3139b6bf8a529328caf64018e9f4.mp4",
              amount: 3824
            },
            {
              id: 23,
              title: "鲁班暴毙",
              poster: "../../../static/images/module/3/pipi_23.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/0c90b63fca93f6f297473e5f5a733301.mp4",
              amount: 4928
            },
            {
              id: 24,
              title: "木兰教学",
              poster: "../../../static/images/module/3/pipi_24.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/dac198a81739787096d42503722e7e65.mp4",
              amount: 2938
            },
            {
              id: 25,
              title: "盘古顺序",
              poster: "../../../static/images/module/3/pipi_25.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/4c49e55ffbda7e6132f118bde08c1e7e.mp4",
              amount: 2742
            },
            {
              id: 26,
              title: "全员毒奶流",
              poster: "../../../static/images/module/3/pipi_26.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/c09ac3979c0eacff28cf1ffb146c988f.mp4",
              amount: 2938
            },
            {
              id: 27,
              title: "上官婉儿合集",
              poster: "../../../static/images/module/3/pipi_27.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/7c6f54098271a334f59b868769dc746e.mp4",
              amount: 4928
            },
            {
              id: 28,
              title: "司马懿教学",
              poster: "../../../static/images/module/3/pipi_28.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/c2faa1e5f40a5482ddb8fb5f22660254.mp4",
              amount: 2938
            },
            {
              id: 29,
              title: "婉儿连招",
              poster: "../../../static/images/module/3/pipi_29.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/5a1c99ec6763d30a81531c9f2309b49b.mp4",
              amount: 2742
            },
            {
              id: 30,
              title: "小乔教学",
              poster: "../../../static/images/module/3/pipi_30.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/5d5834bc0c3b917406bd4f35dd628ddc.mp4",
              amount: 3824
            },
            {
              id: 31,
              title: "养猪流精髓",
              poster: "../../../static/images/module/3/pipi_31.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/aabf5ed6704d5b2e92653adc6479a3cf.mp4",
              amount: 4928
            },
            {
              id: 32,
              title: "虞姬教学",
              poster: "../../../static/images/module/3/pipi_32.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/a275f9a0100224cf51405bb01749c545.mp4",
              amount: 2938
            },
            {
              id: 33,
              title: "钟男神教学",
              poster: "../../../static/images/module/3/pipi_33.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/287821bb47e9615e1c2b4e9471c94859.mp4",
              amount: 2742
            },
            {
              id: 34,
              title: "庄周边路",
              poster: "../../../static/images/module/3/pipi_34.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/88f856e240efcf232d91404b7965d23f.mp4",
              amount: 3824
            },
            {
              id: 35,
              title: "暴击铭文",
              poster: "../../../static/images/module/3/pipi_35.png",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/f7df6f18bde9f3be1f9737e593e4b993.mp4",
              amount: 4928
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
            },
            {
              id: 15,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_15.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 16,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_16.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 17,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_17.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 18,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_18.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 19,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_19.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 20,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_20.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 21,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_21.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 22,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_22.jpg",
              type: "application/x-mpegURL",
              video_url: "",
              amount: 3824
            },
            {
              id: 23,
              title: "变大变小",
              poster: "../../../static/images/module/7/lxy_23.jpg",
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
            },
            {
              id: 15,
              title: "尖叫吧！小酥5",
              poster: "../../../static/images/module/9/mlxs_15.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/065ea4e843f15d05f286f1d7d7a7ee09.m3u8",
              amount: 2616
            },
            {
              id: 16,
              title: "尖叫吧！小酥6",
              poster: "../../../static/images/module/9/mlxs_16.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/1582f2bbef96420ce948d724cc89a184.m3u8",
              amount: 2616
            },
            {
              id: 17,
              title: "流星雨 第1话",
              poster: "../../../static/images/module/9/mlxs_17.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/2681aa600c4df09278119d262b910a78.mp4",
              amount: 2616
            },
            {
              id: 18,
              title: "流星雨 第2话",
              poster: "../../../static/images/module/9/mlxs_18.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/132b415ae8e41546c48a4d867f9e3fc6.m3u8",
              amount: 2616
            },
            {
              id: 19,
              title: "流星雨 第3话",
              poster: "../../../static/images/module/9/mlxs_19.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/a185926281c27e9c2aad65e416a84e6c.m3u8",
              amount: 2616
            },
            {
              id: 20,
              title: "流星雨 第4话",
              poster: "../../../static/images/module/9/mlxs_20.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/a32f2f62511841c381fb11ef1347ac5b.m3u8",
              amount: 2616
            },
            {
              id: 21,
              title: "流星雨 第5话",
              poster: "../../../static/images/module/9/mlxs_21.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/828e216064c9c42d127eff2dba59fa3e.m3u8",
              amount: 2616
            },
            {
              id: 22,
              title: "流星雨 第6话",
              poster: "../../../static/images/module/9/mlxs_22.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/7e659124ffd58614c932433b753c9c40.m3u8",
              amount: 2616
            },
            {
              id: 23,
              title: "流星雨 第7话",
              poster: "../../../static/images/module/9/mlxs_23.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/d2ec359f194a492b828d68a5395e6f64.m3u8",
              amount: 2616
            },
            {
              id: 24,
              title: "流星雨 第8话",
              poster: "../../../static/images/module/9/mlxs_24.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/09e510870dd687c52346e01665378d44.m3u8",
              amount: 2616
            },
            {
              id: 25,
              title: "流星雨 第9话",
              poster: "../../../static/images/module/9/mlxs_25.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/3ba7b927c7a373cefc5baedd71a9e26f.mp4",
              amount: 2616
            },
            {
              id: 26,
              title: "流星雨 结局1",
              poster: "../../../static/images/module/9/mlxs_26.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/12e5ae5fcc74aa16cd20ad6709eb30ea.mp4",
              amount: 2616
            },
            {
              id: 27,
              title: "流星雨 结局2",
              poster: "../../../static/images/module/9/mlxs_27.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/113296b18b66b5da4173ff7f87ab3279.mp4",
              amount: 2616
            },
            {
              id: 28,
              title: "仙人掌女孩 第1话",
              poster: "../../../static/images/module/9/mlxs_28.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/994f847005c88948e27407c5c5a77e49.m3u8",
              amount: 2616
            },
            {
              id: 29,
              title: "仙人掌女孩 第2话",
              poster: "../../../static/images/module/9/mlxs_29.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/aaac6f85e92d84fd84dae30044c80c31.m3u8",
              amount: 2616
            },
            {
              id: 30,
              title: "仙人掌女孩 第3话",
              poster: "../../../static/images/module/9/mlxs_30.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/2e23bbcbcf29ee582142663b1cc522f2.m3u8",
              amount: 2616
            },
            {
              id: 31,
              title: "仙人掌女孩 第4话",
              poster: "../../../static/images/module/9/mlxs_31.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/6603e59433108be081e2535f495a6b20.m3u8",
              amount: 2616
            },
            {
              id: 32,
              title: "仙人掌女孩 第5话",
              poster: "../../../static/images/module/9/mlxs_32.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/8cf4bf2f220bd2020a4893348094ae25.m3u8",
              amount: 2616
            },
            {
              id: 33,
              title: "仙人掌女孩 第6话",
              poster: "../../../static/images/module/9/mlxs_33.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/96120f2bdf9da8499d1caad8c3f73a90.m3u8",
              amount: 2616
            },
            {
              id: 34,
              title: "仙人掌女孩 第7话",
              poster: "../../../static/images/module/9/mlxs_34.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/b8ae3ea2ba36dc229426e9adce6c2e76.mp4",
              amount: 2616
            },
            {
              id: 35,
              title: "仙人掌女孩 第8话",
              poster: "../../../static/images/module/9/mlxs_35.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/7eed0168a941415786b0803ba84bb392.mp4",
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
            },
            {
              id: 15,
              title: "喜力啤酒",
              poster: "../../../static/images/module/10/fktx_15.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/9a2f01d825833b83e5b2d19e8bf56de3.m3u8",
              amount: 3824
            },
            {
              id: 16,
              title: "肌肉男pk绿巨人",
              poster: "../../../static/images/module/10/fktx_16.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/608b6dbe2200dda5500707900e47b6e4.m3u8",
              amount: 4928
            },
            {
              id: 17,
              title: "肌肉男pk小奶狗",
              poster: "../../../static/images/module/10/fktx_17.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/6bcaa2e01b42b8841a48494a9a32b1cf.m3u8",
              amount: 2938
            },
            {
              id: 18,
              title: "禁烟",
              poster: "../../../static/images/module/10/fktx_18.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/9b7b360ce7d471a9efb5a383c7962004.m3u8",
              amount: 2742
            },
            {
              id: 19,
              title: "卡车变形",
              poster: "../../../static/images/module/10/fktx_19.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/077ff7087e5f783fc9430efe84da05be.m3u8",
              amount: 3824
            },
            {
              id: 20,
              title: "开车舞",
              poster: "../../../static/images/module/10/fktx_20.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/84cf23f60b39e7aa5f1e6a1096df85c3.m3u8",
              amount: 4928
            },
            {
              id: 21,
              title: "拉飞机",
              poster: "../../../static/images/module/10/fktx_21.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/aa37cfb24634cc049ad9678357b541e7.m3u8",
              amount: 2938
            },
            {
              id: 22,
              title: "漫威雷神壁纸",
              poster: "../../../static/images/module/10/fktx_22.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/80ce017c93a1f506cc2d82d5399cf5c8.m3u8",
              amount: 3824
            },
            {
              id: 23,
              title: "玫瑰花墙",
              poster: "../../../static/images/module/10/fktx_23.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/7a2650d16dae5830c140d808a82591fa.mp4",
              amount: 4928
            },
            {
              id: 24,
              title: "世界杯酒杯撩妹",
              poster: "../../../static/images/module/10/fktx_24.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/642c9755e736bd53d721e33ec07a11c8.mp4",
              amount: 2938
            },
            {
              id: 25,
              title: "世界杯足球",
              poster: "../../../static/images/module/10/fktx_25.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/5f274b65b3833942158dd0f719054606.mp4",
              amount: 2742
            },
            {
              id: 26,
              title: "双十一口红",
              poster: "../../../static/images/module/10/fktx_26.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/6872fe7af2a0b7ff9706409a3be52570.mp4",
              amount: 2938
            },
            {
              id: 27,
              title: "水龙",
              poster: "../../../static/images/module/10/fktx_27.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/4eae0d7db3d9b3ff14e42e7346303c3f.mp4",
              amount: 4928
            },
            {
              id: 28,
              title: "泰坦尼克号女友分手",
              poster: "../../../static/images/module/10/fktx_28.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/f61f89d9c90d6f9235fe4b45a8bb41d9.m3u8",
              amount: 2938
            },
            {
              id: 29,
              title: "铁皮系列片二 停车场被打",
              poster: "../../../static/images/module/10/fktx_29.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/1e112c6b40cc180ff31dd8f62615a6ea.m3u8",
              amount: 2938
            },
            {
              id: 30,
              title: "铁皮系列片三 篮球樱木",
              poster: "../../../static/images/module/10/fktx_30.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/9d86a5c1b56dcf7f786f28e8db1f8861.m3u8",
              amount: 4928
            },
            {
              id: 31,
              title: "铁皮系列片一 铁皮变车",
              poster: "../../../static/images/module/10/fktx_31.jpg",
              type: "application/x-mpegURL",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/m3u8/adaptive/28028bdfef2f793113fed6f723171d0f.m3u8",
              amount: 2938
            },
            {
              id: 32,
              title: "万圣节南瓜灯",
              poster: "../../../static/images/module/10/fktx_32.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/8f94d32125d40c73df69800ee09cceaa.mp4",
              amount: 4928
            },
            {
              id: 33,
              title: "微博-挑战舞蹈",
              poster: "../../../static/images/module/10/fktx_33.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/88d1134c1467b846d0d1a75729001aa4.mp4",
              amount: 2938
            },
            {
              id: 34,
              title: "下掉-教师节",
              poster: "../../../static/images/module/10/fktx_34.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/00725def97bfcd22350d0815dcc8ef46.mp4",
              amount: 2742
            },
            {
              id: 35,
              title: "一百个足球",
              poster: "../../../static/images/module/10/fktx_35.jpg",
              type: "video/mp4",
              video_url:
                "https://38917.long-vod.cdn.aodianyun.com/u/38917/mp4/0x0/f20f526ae0299ebf7961197d8d811fa9.mp4",
              amount: 3824
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
