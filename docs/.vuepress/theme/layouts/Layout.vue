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
          <p><a :href="live.link" target="_blank" rel="nofollow">2024.6.13 · Vue Shenzhen Live</a></p>
          <p>Meetup Online</p>
        </h5>
        <!-- <a class="register-btn" href="http://hdxu.cn/kj1pf" target="_blank" rel="nofollow"
          >Register now · 立刻报名</a
        > -->
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
            进入<a :href="live.link" target="_blank" rel="nofollow">{{
              live.name
            }}</a
            >线上参与
          </p>
          <h2>GUEST SPEAKER · 邀请嘉宾</h2>
          <host-list :hosts="hostList" />
          <h2>TOPICS · 分享议题</h2>
          <topic-list :topics="topicList" />
          <p>
            您可以在<a :href="quiz.link" target="_blank" rel="nofollow">{{
              quiz.name
            }}</a
            >中留下感兴趣的问题，活动嘉宾将在线上直播为您解答。
          </p>
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
      time: "2024年6月13日 周四 19:00",
      live: {
        name: "VueShenZhen直播间",
        link: "https://live.bilibili.com/23180029",
      },
      quiz: {
        name: "问卷收集",
        link: "https://www.wjx.cn/vj/Q0nTXFd.aspx",
      },
      contact: "扫码关注 VUE SHENZHEN 公众号",
      hostList: [
        {
          hostName: "曾令卡",
          hostDesc: "华为云高级前端工程师, OpenTiny开源社区负责人, TinyVue跨端跨框架组件库核心贡献者。",
          portraitUrl: "/assets/images/zenglinka.jpg",
          link: "https://github.com/kagol",
        },
      ],
      topicList: [
        {
          title: "OpenTiny跨框架组件库实现原理：跨Vue、React、Solid原理解析",
          schedule: "19:00 - 20:00",
          description:
            "实现组件库跨框架技术是一种提高Web页面开发效率和应用灵活性非常重要的方法。随着前端技术的快速发展，组件库和框架的种类也日益繁多，因此，实现组件库跨框架技术对解决开发痛点、降低开发成本有重要意义。本次分享主要介绍OpenTiny组件库的核心优势和设计理念，并带大家动手实践一个跨Vue、React、Solid框架的mini组件库。",
        },
      ],
      reviewList: [
        {
          title: "2022.5.28 Vue Shenzhen Meetup （嘉宾：莫春辉）",
          link:
            "https://live.juejin.cn/4354/2914001",
        },
        {
          title: "2021.2.24 Vue Shenzhen Meetup （嘉宾：Eduardo San Martin）",
          link:
            "https://www.bilibili.com/video/BV1CT4y1Q7kE",
        },
        {
          title: "2021.12.30 Vue Shenzhen Meetup （嘉宾：戴威）",
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
