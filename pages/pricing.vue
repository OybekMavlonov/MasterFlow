<template>
  <div class="pricing-wrapper">
    <div class="pricing-intro">
      <v-container>
        <v-row>
          <v-col class="text-center">
            <h1>Our plans for your strategies.</h1>
            <p>
              See below our three main plans for your business, for your stratup
              and agency. It starts from here! You can teach yourself what you
              really like.
            </p>
            <div class="bill">
              <span class="monthly">Bill Monthly</span>
              <label class="switch">
                <input type="checkbox" />
                <span class="slider round"></span>
              </label>
              <span class="annually">Bill Annually</span>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="pricing-list">
      <v-container>
        <v-row>
          <v-col md="4" v-for="item in priceItems" :key="item.value">
            <div class="pricing-card">
              <div class="pricing-list__item">
                <div class="price">
                  <span class="value">{{ item.value }}</span>
                  <span class="month">/ month</span>
                </div>
                <div class="category">
                  {{ item.category }}
                </div>
                <div class="item-info">
                  {{ item.info }}
                </div>
                <ul class="advantages">
                  <li
                    v-for="(advantage, index) in item.advantages"
                    :key="index"
                  >
                    <div class="tick"></div>
                    <img
                      src="../assets/images/tick.png"
                      alt="tick"
                      class="tick-img"
                    />
                    {{ advantage }}
                  </li>
                </ul>
                <a href="#" class="get">Get {{ item.category }}</a>
              </div>
            </div>
            <img
              src="../assets/images/CombinedShape.png"
              alt="shape"
              class="pricing-shape"
            />
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="services">
      <v-container>
        <div class="premium"><span>premium</span></div>
        <h1>What services do our rate plans include?</h1>
        <v-row>
          <v-col md="6" v-for="item in services" :key="item.name">
            <div class="services-item">
              <div class="services-item__img" :class="item.class">
                <img :src="item.img" alt="up" />
              </div>
              <div class="services-item__info">
                <h3>{{ item.name }}</h3>
                <p>
                  {{ item.text }}
                </p>
              </div>
            </div>
          </v-col>
        </v-row>

        <div class="customers-logo">
          <img
            v-for="(logo, index) in brandLogo"
            :key="index"
            :src="logo"
            alt="brandlogo"
          />
        </div>
      </v-container>
    </div>

    <div class="questions">
      <v-container>
        <h1>The most asked questions</h1>
        <div
          class="questions-card"
          v-for="(question, index) in questions"
          :key="index"
        >
          <a href="#">{{ question }}</a>
        </div>
      </v-container>
    </div>

    <Experience></Experience>
    <Subscribe :title="buyTitle" :button="downloadButton"></Subscribe>
    <Footer :socialIcons="socialIcons"></Footer>
  </div>
</template>

<script>
import Experience from "~/components/Experience.vue";
import Subscribe from "~/components/Subscribe.vue";
import Footer from "~/components/Footer.vue";

export default {
  data() {
    return {
      priceItems: [
        {
          value: "$29",
          category: "easy",
          info: "All the basics for businesses that are just getting started.",
          advantages: ["One project", "Your dashboard"]
        },
        {
          value: "$59",
          category: "basic",
          info: "Better for growing businesses that want more customers.",
          advantages: [
            "Two project",
            "Your dashboard",
            "Components included",
            "Advanced charts"
          ]
        },
        {
          value: "$139",
          category: "custom",
          info: "Advanced features for pros who need more customization.",
          advantages: [
            "Unlimited project",
            "Your dashboard",
            "+300 components",
            "Chat support",
            "Guaranteed 100%",
            "Unlimited users"
          ]
        }
      ],
      services: [
        {
          img: require("../assets/images/trending-up.png"),
          class: "trending",
          name: "Analytics Tools",
          text:
            "With analytics tools, to help you share with current and future clients."
        },
        {
          img: require("../assets/images/dollar-sign.png"),
          class: "dollar",
          name: "Total Collections",
          text:
            "Total collections, quoting, enrollment, and reporting in Italian and English."
        },
        {
          img: require("../assets/images/globe.png"),
          class: "globe",
          name: "All Services",
          text:
            "All services for our team of industry experts, personal training, support line and help desk."
        },
        {
          img: require("../assets/images/monitor.png"),
          class: "monitor",
          name: "Work With Us",
          text:
            "We can help you set up and manager your groups if you are become our partner."
        }
      ],
      brandLogo: [
        require("../assets/images/slack.png"),
        require("../assets/images/netflix.png"),
        require("../assets/images/fitbit.png"),
        require("../assets/images/google.png"),
        require("../assets/images/airbnb.png")
      ],
      questions: [
        "Can I make a free plan to get started?",
        "My team wants to have a direct chat with you. How to do it?",
        "How can I work with you and become your partner?",
        "What services do your rate plans include?",
        "How can i cancel all my accounts? With Custom plan."
      ],
      buyTitle: "Buy now Master Flow!",
      downloadButton: "Download",
      socialIcons: [
        { name: "fb", img: require("../assets/images/facebook.png") },
        { name: "twitter", img: require("../assets/images/twitter.png") },
        { name: "instagram", img: require("../assets/images/instagram.png") }
      ]
    };
  },
  components: {
    Experience,
    Subscribe,
    Footer
  }
};
</script>

<style lang="scss">
.pricing-wrapper {
  .pricing-intro {
    padding: 100px 80px;

    h1 {
      margin-bottom: 10px;
      @extend .title;
    }
    p {
      padding: 0 230px;
      @extend .text;
    }
    .bill {
      margin-top: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      span {
        font-family: Gilroy;
        font-style: normal;
        font-weight: 600;
        font-size: 16px;
        line-height: 19px;
        color: #0a083b;
      }
      .switch {
        position: relative;
        display: inline-block;
        width: 60px;
        height: 34px;
        margin: 0 17px;
        input {
          opacity: 0;
          width: 0;
          height: 0;
        }

        .slider {
          position: absolute;
          cursor: pointer;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          background-color: #ccc;
          -webkit-transition: 0.4s;
          transition: 0.4s;

          &:before {
            position: absolute;
            content: "";
            height: 26px;
            width: 26px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            -webkit-transition: 0.4s;
            transition: 0.4s;
          }
        }
      }

      input:checked + .slider {
        background-color: #175cff;
      }

      input:focus + .slider {
        box-shadow: 0 0 1px #175cff;
      }

      input:checked + .slider:before {
        -webkit-transform: translateX(26px);
        -ms-transform: translateX(26px);
        transform: translateX(26px);
      }

      /* Rounded sliders */
      .slider.round {
        border-radius: 34px;
      }

      .slider.round:before {
        border-radius: 50%;
      }
    }
  }

  .pricing-list {
    margin-bottom: 50px;
    &__item {
      padding: 40px 46px;
      border-radius: 4px;
      border: 1px solid #e5e5e5;
      &:hover .price .value {
        color: #36b37e;
      }
      .price {
        .value {
          font-family: Gilroy;
          font-style: normal;
          font-weight: 600;
          font-size: 36px;
          line-height: 42px;
          color: #0a083b;
        }
        .month {
          font-family: Gilroy;
          font-style: normal;
          font-weight: 600;
          font-size: 14px;
          line-height: 18px;
          color: #57586e;
        }
      }
      .category {
        font-family: Gilroy;
        font-style: normal;
        font-weight: 600;
        font-size: 26px;
        line-height: 30px;
        color: #0a083b;
        padding: 14px 0 10px;
        text-transform: capitalize;
      }
      .item-info {
        font-family: Gilroy;
        font-style: normal;
        font-weight: normal;
        font-size: 15px;
        line-height: 24px;
        color: #57586e;
        padding-bottom: 16px;
        border-bottom: 1px solid rgba(0, 0, 0, 0.6);
      }
      .advantages {
        list-style-type: none;
        padding: 20px 0;

        li {
          font-family: Gilroy;
          font-style: normal;
          font-weight: 600;
          font-size: 15px;
          line-height: 18px;
          color: #0a083b;
          position: relative;
          margin-bottom: 18px;

          .tick {
            display: inline;
            background: #36b37e;
            mix-blend-mode: normal;
            opacity: 0.15;
            padding: 3px 12px;
            border-radius: 50%;
            margin-right: 10px;
          }
          .tick-img {
            position: absolute;
            left: 8px;
            top: 4px;
          }
        }
      }
      .get {
        border: 2px solid #175cff;
        padding: 15px 40px;
        @extend .button;

        &:hover {
          background: #175cff;
          color: #fff;
        }
      }
    }
    .pricing-shape {
      display: none;
    }
    .col-md-4:nth-child(3) {
      position: relative;
      .pricing-shape {
        display: inline;
        position: absolute;
        bottom: -28px;
        left: -30px;
      }
      // .pricing-list__item {
      &:after {
        // content: url("../assets/images/CombinedShape.png");
        position: absolute;
        bottom: -50px;
        left: -44px;
        z-index: 0;
      }
      // }
    }
  }

  .services {
    padding: 80px 0;

    .premium {
      display: flex;
      justify-content: center;
      span {
        background: rgba(23, 92, 255, 0.1);
        border-radius: 2000px;
        padding: 6px 20px;
        font-family: Gilroy;
        font-style: normal;
        font-weight: bold;
        font-size: 13px;
        line-height: 16px;
        text-transform: uppercase;
        text-align: center;
        letter-spacing: 1px;
        color: #175cff;
      }
    }
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
      .dollar {
        padding: 16px 22px;
      }
      .globe {
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

  .questions {
    background: rgb(23, 21, 75);
    padding: 50px 0;

    h1 {
      color: #fff;
      text-align: center;
      margin-bottom: 30px;
      @extend .title;
    }

    &-card {
      margin: 20px 0;
      background: rgba(255, 255, 255, 0.06);
      box-shadow: 0px 20px 40px rgba(3, 0, 77, 0.04);
      border-radius: 8px;
      padding: 30px 36px;

      a {
        font-family: Gilroy;
        font-style: normal;
        font-weight: bold;
        font-size: 16px;
        line-height: 20px;
        letter-spacing: 0.2px;
        color: #ffffff;
      }
    }
  }
}
</style>
