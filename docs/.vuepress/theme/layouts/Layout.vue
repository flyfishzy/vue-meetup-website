<template>
  <section class="theme-container">
    <div id="theme-banner">
      <img
        alt="深圳"
        src="/assets/images/banner-back.png"
        class="banner-background-img"
      />
      <div class="banner-container">
        <img
          id="banner"
          alt="vueshenzhen"
          src="/assets/images/banner-main.png"
          class="banner-img"
        />
        <img alt="vue.js" src="/assets/images/v-logo.png" class="banner-logo" />
        <h1>VUE SHENZHEN · 深圳</h1>
        <h5>
          <p><a :href="live.link" target="_blank" rel="nofollow">2024.7.10 · Vue Shenzhen</a></p>
          <p>线下 Meetup（名额有限，先到先得）</p>
        </h5>
        <a class="register-btn" href="https://www.huodongxing.com/event/1763562540800" target="_blank" rel="nofollow"
          >Register now · 立刻报名</a
        >
      </div>
    </div>
    <div id="theme-body">
      <div class="body-divider-back"></div>
      <div class="body-divider-box">
        <div class="body-divider"></div>
      </div>
      <div class="body-container">
        <img
          alt="top-img"
          src="/assets/images/body-top.png"
          class="body-top-img"
        />
        <div class="body-box">
          <h2>ABOUT US · 关于我们</h2>
          <p>{{ description }}</p>
          <h2>LATEST · 最新活动</h2>
          <p>
            <span
              ><img
                src="/assets/images/time-icon.png"
                class="body-box-time-icon"/></span
            ><span>{{ time }}</span>
          </p>
          <p>
            <!-- 进入<a :href="live.link" target="_blank" rel="nofollow">{{
              live.name
            }}</a -->
            线下参与，和antfu面对面交流
          </p>
          <p>地点：深圳天安云谷1栋A座</p>
          <h2>GUEST SPEAKER · 邀请嘉宾</h2>
          <host-list :hosts="hostList" />
          <h2>TOPICS · 分享议题</h2>
          <topic-list :topics="topicList" />
          <!-- <p>
            您可以在<a :href="quiz.link" target="_blank" rel="nofollow">{{
              quiz.name
            }}</a
            >中留下感兴趣的问题，活动嘉宾将在线上直播为您解答。
          </p> -->
          <h2>REVIEW · 往期回顾</h2>
          <review-list :reviews="reviewList" />
          <h2 style="margin-bottom: 3vw">CONTACT US · 联系我们</h2>
          <div class="body-box-code">
            <img
              alt="vueshenzhen-code"
              src="/assets/images/vuesz-code.gif"
              class="body-box-code-img"
            />
            <div class="body-box-code-slogan">{{ contact }}</div>
          </div>
        </div>
        <div class="body-box-sponsor">
          <h2>PARTNERS · 合作伙伴</h2>
          <partner-list :partners="partnerList" />
        </div>
        <img
          alt="bottom-img"
          src="/assets/images/body-bottom.png"
          class="body-bottom-img"
        />
      </div>
    </div>
  </section>
</template>

<script>
import HostList from "../components/HostList.vue";
import PartnerList from "../components/PartnerList.vue";
import TopicList from "../components/TopicList.vue";
import ReviewList from "../components/ReviewList.vue";

export default {
  components: {
    TopicList,
    HostList,
    PartnerList,
    ReviewList,
  },
  data() {
    return {
      description:
        "Vue Shenzhen 是由一群 Vue.js 开发爱好者自发成立的位于深圳的本地组织，旨在将热情的 Vue.js 开发人员联系起来共同学习和成长。",
      time: "2024年7月10日 周三 19:00",
      live: {
        name: "VueShenZhen直播间",
        link: "https://live.bilibili.com/23180029",
      },
      quiz: {
        name: "问卷收集",
        link: "https://www.wjx.cn/vm/hHya7J3.aspx",
      },
      contact: "扫码关注 VUE SHENZHEN 公众号",
      hostList: [
        {
          hostName: "Anthony Fu",
          hostDesc: "Anthony Fu 是一位狂热的开源爱好者和技术创造者。他目前在 NuxtLabs 工作，并是 Vue、Nuxt 和 Vite 的核心团队成员。",
          portraitUrl: "/assets/images/antfu.png",
          link: "https://github.com/antfu",
        },
      ],
      topicList: [
        {
          title: "The Set Theory 集合论",
          schedule: "19:00 - 20:00",
          description:
            "Anthony 在全职从事开源工作的过程中学到的经验教训。包含使开源项目更成功的技巧和想法。",
        },
      ],
      reviewList: [
       {
          title: "2024.6.13 OpenTiny跨框架组件库实现原理（嘉宾：曾令卡）",
          link:
            "https://www.bilibili.com/video/BV1Ys421T7Ns",
        },
        {
          title: "2022.5.28 开启个性化DIY低代码平台新纪元 （嘉宾：莫春辉）",
          link:
            "https://live.juejin.cn/4354/2914001",
        },
        {
          title: "2021.2.24 Beyond state management with Pinia （嘉宾：Eduardo San Martin）",
          link:
            "https://www.bilibili.com/video/BV1CT4y1Q7kE",
        },
        {
          title: "2021.12.30 Vue3 Virtual DOM性能优化 （嘉宾：戴威）",
          link:
            "https://www.bilibili.com/video/BV1uT4y1m7cs?share_source=copy_web",
        },
        {
          title: "2021.10.28 Vue Shenzhen Meetup （嘉宾：Anthony Fu）",
          link:
            "https://www.bilibili.com/video/BV1jL4y1q76J?share_source=copy_web",
        },
        {
          title: "2021.08.21 Vue Shenzhen Meetup （嘉宾：林成璋、王鹏）",
          link:
            "https://www.bilibili.com/video/BV17L411b7gd?share_source=copy_web",
        }
      ],
      partnerList: [
        {
          name: "掘金",
          logo: "/assets/images/juejin-logo.png",
          link: "https://www.juejin.cn",
          key: "juejin",
        },
        {
          name: "活动行",
          logo: "/assets/images/huodongx-logo.png",
          link: "https://www.huodongxing.com/",
          key: "huodongx",
        },
        {
          name: "开源中国",
          logo: "/assets/images/oschina-logo.svg",
          link: "https://www.oschina.net/",
          key: "oschina",
        },
        {
          name: "哔哩哔哩视频",
          logo: "/assets/images/bilibili-logo.png",
          link: "https://www.bilibili.com/",
          key: "bilibili",
        },
        {
          name: "思否",
          logo: "/assets/images/segmentfault-logo.svg",
          link: "https://segmentfault.com/",
          key: "segmentfault",
        },
      ],
    };
  },
};
</script>

<style src="../styles/index.css" scoped></style>
