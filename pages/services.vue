<template>
  <div class="services-wrapper">
    <div class="services-intro">
      <v-container>
        <v-row>
          <v-col class="text-center">
            <h1>We help startups and agencies to achieve their goal.</h1>
            <p>
              Minimalism, optimization and precision, your business is
              skyrocketing.
            </p>
            <div class="buttons">
              <a href="#" class="started">Get started</a>
              <a href="#" class="learn-more">Learn more</a>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="services-img">
      <v-container>
        <v-row>
          <v-col md="7">
            <div class="left">
              <img src="../assets/images/service1.png" alt="service1" />
            </div>
          </v-col>
          <v-col md="5">
            <div class="right">
              <div class="bg">
                <img src="../assets/images/service2.png" alt="service2" />
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="who">
      <v-container>
        <div class="who-wrapper">
          <div class="blue-text">WHO WE ARE</div>
          <v-row>
            <v-col cols="12" sm="8" md="6">
              <div class="left">
                <h1>Read who we are and What we do on the web.</h1>
              </div>
            </v-col>
            <v-col cols="12" sm="8" md="6">
              <div class="right">
                <p>
                  We bring the results while helping you achieve cost and time
                  savings without taking on risk or management overhead. Our
                  team provides high-level creative education.
                </p>
                <p>
                  If you’re going to go with a minimalist style in just one area
                  of the home, then choose your home office. A clean and clearly
                  organised workspace is conductive to great concentration and
                  an uninterrupted workflow.
                </p>
                <p>
                  Less visual clutter leads to less mental clutter, and you will
                  be able to find your needed files and equipment a whole lot
                  faster too.
                </p>
              </div>
            </v-col>
          </v-row>
        </div>
      </v-container>
    </div>

    <div class="strategies">
      <v-container>
        <v-row>
          <v-col cols="12" sm="8" md="6">
            <div class="left">
              <img
                src="../assets/images/habitShape.png"
                class="strategy-shape"
                alt="strategy"
              />
              <img
                src="../assets/images/strategy-img.png"
                class="strategy-img"
                alt="strategy-img"
              />
            </div>
          </v-col>
          <v-col cols="12" sm="8" md="6">
            <div class="right">
              <h1>The strategies of Our business</h1>
              <p>
                “Design is not just what it looks like and feels like. Design is
                how it works”. We always try to make a great output by this
                culture. Steve Jobs.
              </p>
              <p>
                See below our three main plans for your business, for your
                stratup and agency. It starts from here! You can teach yourself
                what you really like.
              </p>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="clients-work">
      <v-container>
        <h1>What we do and how we do our clients' works</h1>
        <v-row>
          <v-col md="6" v-for="item in clientsWork" :key="item.name">
            <div class="clients-work-item">
              <div class="clients-work-item__img" :class="item.class">
                <img :src="item.img" alt="up" />
              </div>
              <div class="clients-work-item__info">
                <h3>{{ item.name }}</h3>
                <p>
                  {{ item.text }}
                </p>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="team">
      <v-container>
        <div class="blue-text">Our Members</div>
        <h1>Who is part of Master Flow.</h1>
        <h1>Our team of experts.</h1>
        <v-row>
          <v-col md="4" v-for="expert in team" :key="expert.name">
            <div class="expert">
              <img :src="expert.img" :alt="expert.name" />
              <div class="name">{{ expert.name }}</div>
              <h4 class="position">{{ expert.position }}</h4>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <Subscribe :title="resourcesTitle" :button="resourcesButton"></Subscribe>
    <Footer :socialIcons="socialIcons"></Footer>
  </div>
</template>

<script>
import Subscribe from "~/components/Subscribe.vue";
import Footer from "~/components/Footer.vue";

export default {
  data() {
    return {
      clientsWork: [
        {
          img: require("../assets/images/ui.png"),
          class: "ui",
          name: "UI Design",
          text:
            "With analytics tools, to help you share with current and future clients."
        },
        {
          img: require("../assets/images/trending-up.png"),
          class: "ux",
          name: "UX Strategy",
          text:
            "Total collections, quoting, enrollment, and reporting in Italian and English."
        },
        {
          img: require("../assets/images/korzinka.png"),
          class: "branding",
          name: "Branding",
          text:
            "All services for our team of industry experts, personal training, support line and help desk."
        },
        {
          img: require("../assets/images/monitor.png"),
          class: "monitor",
          name: "Web Development",
          text:
            "We can help you set up and manager your groups if you are become our partner."
        }
      ],
      team: [
        {
          img: require("../assets/images/member1.png"),
          name: "Marc Stewart",
          position: "Founder and Developer"
        },
        {
          img: require("../assets/images/member2.png"),
          name: "Lisa Lennon",
          position: "Product Designer"
        },
        {
          img: require("../assets/images/member3.png"),
          name: "Pedro Stols",
          position: "Front-End Developer"
        },
        {
          img: require("../assets/images/member4.png"),
          name: "Alberto Ferdy",
          position: "Motion Designer"
        },
        {
          img: require("../assets/images/member5.png"),
          name: "Sofia Smith",
          position: "UX Designer"
        },
        {
          img: require("../assets/images/member6.png"),
          name: "Mario Catrone",
          position: "Back-End Developer"
        }
      ],
      resourcesTitle: "Free resources for you!",
      resourcesButton: "Submit",
      socialIcons: [
        { name: "fb", img: require("../assets/images/facebookBlack.png") },
        { name: "twitter", img: require("../assets/images/twitterBlack.png") },
        {
          name: "instagram",
          img: require("../assets/images/instagramBlack.png")
        }
      ]
    };
  },
  components: {
    Subscribe,
    Footer
  }
};
</script>

<style lang="scss">
.services-wrapper {
  .services-intro {
    padding: 100px 80px;

    h1 {
      margin-bottom: 10px;
      padding: 0 20%;
      @extend .title;
    }
    p {
      padding: 0 230px;
      @extend .text;
    }
    .buttons {
      display: flex;
      justify-content: center;
      a {
        @extend .button;
      }
      .started {
        background: #175cff;
        color: #fff;
        margin-right: 16px;
      }
      .learn-more {
        color: #175cff;
        border: 2px solid #e5e5e5;
      }
    }
  }

  .services-img {
    margin-bottom: 50px;

    .left {
      position: relative;

      img {
        width: 650px;
        height: 400px;
        box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        border-radius: 4px;
      }

      &::after {
        content: url("../assets/images/subscribeShape.png");
        position: absolute;
        top: -42px;
        left: 90px;
      }
    }

    .right {
      position: relative;
      .bg {
        position: relative;
        width: 430px;
        height: 400px;
        background: rgb(23, 21, 75);
        transform: translate(40px, 40px);
        border-radius: 0px;
        box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
      }
      img {
        width: 430px;
        height: 400px;
        box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        border-radius: 4px;
        transform: translate(-40px, -40px);
      }
    }
  }

  .who {
    &-wrapper {
      padding: 70px 0;
      .left {
        h1 {
          padding-right: 30px;
          @extend .title;
        }
      }
      .right {
        p {
          padding: 10px 0 10px 10px;
          margin: 0;
          @extend .text;
        }
      }
    }
  }

  .strategies {
    margin-left: 100px;
    background: #f4f4f4;
    padding: 80px;
    margin-bottom: 110px;
    .left {
      position: relative;
      .strategy-shape {
        position: absolute;
        top: 467px;
        left: 70px;
        width: 90px;
        height: 70px;
      }
      position: relative;
      .strategy-img {
        position: absolute;
        border-radius: 4px;
        width: 420px;
        height: 500px;
        box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
      }
    }
    .right {
      padding-right: 100px;
      h1 {
        @extend .title;
      }
      p {
        padding: 0;
        @extend .text;
      }
    }
  }

  .clients-work {
    padding: 60px 0;

    h1 {
      text-align: center;
      padding: 0 26%;
      margin: 10px 0 30px;
      @extend .title;
    }

    &-item {
      display: flex;
      &__img {
        padding: 16px 12px;
        width: 62px;
        background: rgba(23, 92, 255, 0.04);
        height: 62px;
        border-radius: 8px;
        margin-right: 20px;
      }
      .ui {
        padding: 16px 22px;
      }
      .branding {
        padding: 16px 17px;
      }
      .monitor {
        padding: 16px;
      }
      &__info {
        padding-top: 16px;
        h3 {
          font-family: Gilroy;
          font-style: normal;
          font-weight: 600;
          font-size: 22px;
          line-height: 24px;
          color: #0a083b;
          margin-bottom: 6px;
        }
        p {
          font-family: Gilroy-Regular;
          font-style: normal;
          font-weight: normal;
          font-size: 18px;
          padding-right: 90px;
          line-height: 28px;
          color: #57586e;
        }
      }
    }

    .customers-logo {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 60px;
      width: 93%;
    }
  }

  .team {
    padding: 30px 0 80px;
    h1 {
      line-height: 50px;
      @extend .title;

      &:nth-child(3) {
        margin-bottom: 40px;
      }
    }

    .expert {
      img {
        width: 340px;
        height: 420px;
        box-shadow: 0px 20px 40px 0px rgba(0, 0, 0, 0.04);
        border-radius: 4px;
      }
      .name {
        font-family: Gilroy;
        font-style: normal;
        font-weight: 600;
        font-size: 14px;
        line-height: 18px;
        color: #57586e;
        opacity: 0.3;
        margin: 12px 0 2px;
      }
      .position {
        font-family: Gilroy;
        font-style: normal;
        font-weight: 600;
        font-size: 20px;
        line-height: 30px;
        color: #0a083b;
      }
    }
  }
  .subscribe {
    .newsletter-wrapper {
      .newsletter {
        background: #17154b;
      }
    }
  }

  footer {
    border-top: 1px solid rgba(10, 8, 59, 0.08);
    margin-top: 40px;
    background: #fff !important;

    .footer-main {
      border-bottom: 1px solid rgba(10, 8, 59, 0.08);
      .logo {
        h1 {
          color: #0a083b;
        }
      }
      .number,
      .support,
      .menu {
        color: #0a083b;
      }
      .menu-items {
        a {
          color: rgba(87, 88, 110, 0.8);
        }
      }
    }
    .footer-bottom {
      .social-logos a {
        border: 1.4px solid #0a083b;
      }
      .rights {
        color: #0a083b;
      }
    }
  }
}
</style>
