<template>
  <div class="wrapper">
    <div class="home-main">
      <v-container>
        <v-row>
          <v-col cols="12" sm="8" md="6">
            <div class="left">
              <div class="welcome">welcome!</div>
              <h1>The best way for your startup.</h1>
              <p>
                You can create your own design process with master. They are
                blocks designed to carry on with the times with your customers.
                Modern, minimal blocks with a cool look.
              </p>
              <div class="buttons">
                <a href="#" class="started">Get started</a>
                <a href="#" class="learn-more">Learn more</a>
              </div>
            </div>
          </v-col>
          <v-col cols="12" sm="8" md="6">
            <div class="right">
              <img
                class="shape"
                src="../assets/images/CombinedShape.png"
                alt=""
              />
              <div class="bg">
                <button>
                  <img src="../assets/images/Triangle.png" alt="triangle" />
                </button>
                <img
                  class="home-img"
                  src="../assets/images/home-img.png"
                  alt=""
                />
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="customers">
      <v-container>
        <div class="customers-wrapper">
          <div class="blue-text">Our Customers</div>
          <v-row>
            <v-col cols="12" sm="8" md="6">
              <div class="left">
                <h1>We have worked with them. Our super customers.</h1>
              </div>
            </v-col>
            <v-col cols="12" sm="8" md="6">
              <div class="right">
                <p>
                  We bring the results while helping you achieve cost and time
                  savings without taking on risk or management overhead. Our
                  team provides high-level creative education.
                </p>
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
        </div>
      </v-container>
    </div>

    <div class="office">
      <v-container>
        <v-row>
          <v-col cols="12" sm="8" md="6">
            <div class="left">
              <img
                class="shape"
                src="../assets/images/CombinedShape.png"
                alt=""
              />
              <div class="office-img__wrapper">
                <img
                  class="office-img1"
                  src="../assets/images/image1.png"
                  alt="office"
                />
                <img
                  class="office-img2"
                  src="../assets/images/image2.png"
                  alt="office"
                />
              </div>
            </div>
          </v-col>
          <v-col cols="12" sm="8" md="6">
            <div class="right">
              <h1>We work in Minimal Offices</h1>
              <p>
                If you’re going to go with a minimalist style in just one area
                of the home, then choose your home office. A clean and clearly
                organised workspace is conductive to great concentration and an
                uninterrupted workflow. Less visual clutter leads to less mental
                clutter, and you will be able to find your needed files and
                equipment a whole lot faster too.
              </p>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div class="habits">
      <v-container>
        <v-row>
          <v-col cols="12" sm="8" md="6">
            <div class="left">
              <h1>The habits of Our Startup</h1>
              <p>
                “Design is not just what it looks like and feels like. Design is
                how it works”. We always try to make a great output by this
                culture. Steve Jobs.
              </p>
              <ul>
                <li v-for="(item, index) in habitList" :key="index">
                  <img :src="habitListIcon" alt="tick" />{{ item }}
                </li>
              </ul>
            </div>
          </v-col>
          <v-col cols="12" sm="8" md="6">
            <div class="right">
              <img
                src="../assets/images/habitShape.png"
                class="habit-shape"
                alt="habitShape"
              />
              <img
                src="../assets/images/habit-img.png"
                class="habit-img"
                alt="habit-img"
              />
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <Experience></Experience>

    <Subscribe :title="subscribeTitle" :button="subscribeButton"></Subscribe>

    <div class="magic">
      <v-container>
        <v-row>
          <v-col cols="12" sm="8" md="6">
            <div class="left">
              <h1>Some magic tricks for your phone</h1>
              <p>
                Stream real-time video of your home, and receive notificatoins
                whenever motion is detected, with Canary’s 1080p HD camera.
                Perfect device way.
              </p>
              <div class="buttons">
                <a href="#" class="how-works">How it works</a>
                <a href="#" class="our-blog">Our Blog</a>
              </div>
            </div>
          </v-col>
          <v-col cols="12" sm="8" md="6">
            <div class="right">
              <img
                class="shape1"
                src="../assets/images/CombinedShape.png"
                alt=""
              />
              <img
                class="shape2"
                src="../assets/images/CombinedShape.png"
                alt=""
              />
              <div class="magic-img__wrapper">
                <img
                  class="magic-img1"
                  src="../assets/images/magic1.png"
                  alt="magic"
                />
                <img
                  class="magic-img2"
                  src="../assets/images/magic2.png"
                  alt="magic"
                />
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

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
      brandLogo: [
        require("../assets/images/slack.png"),
        require("../assets/images/netflix.png"),
        require("../assets/images/fitbit.png"),
        require("../assets/images/google.png"),
        require("../assets/images/airbnb.png")
      ],
      habitList: [
        "50 Blocks",
        "Only Explorations",
        "Teamwork Always",
        "Communications",
        "Weekly Analytics",
        "Update for Brand"
      ],
      habitListIcon: require("../assets/images/tick.png"),
      subscribeTitle: "Subscribe to the newsletter!",
      subscribeButton: "Submit",
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
.wrapper {
  .home-main {
    .left {
      padding: 150px 106px 150px 0;
      .welcome {
        @extend .blue-text;
      }
      h1 {
        font-size: 52px;
        line-height: 62px;
        @extend .title;
      }
      p {
        line-height: 26px;
        margin: 18px 0 26px;
        @extend .text;
      }
      .buttons {
        display: flex;
        justify-content: flex-start;
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
    .right {
      position: relative;
      .shape {
        width: 70px;
        height: 90px;
        position: absolute;
        bottom: 100px;
        left: 40px;
      }

      .bg {
        width: 500px;
        height: 590px;
        transform: translate(124px, -12px);
        background: #17154b;
        border-radius: 0px;
        position: relative;

        button {
          position: absolute;
          top: 53%;
          z-index: 9;
          left: 32%;
          padding: 20px 22px 14px 27px;
          background: #fff;
          border-radius: 50%;
          box-shadow: 0px 4px 12px 0px #000000 10%;

          &:focus {
            outline: none;
          }
        }

        .home-img {
          width: 500px;
          height: 590px;
          transform: translate(-45px, 40px);
          border-radius: 4px;
          box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        }
      }
    }
  }

  .customers {
    &-wrapper {
      padding: 100px 0;
      border-bottom: 1px solid rgba(0, 0, 0, 0.08);
      .left {
        h1 {
          @extend .title;
        }
      }
      .right {
        p {
          padding: 10px 0 10px 10px;
          @extend .text;
        }
      }
      .customers-logo {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 40px;
        width: 93%;
      }
    }
  }

  .office {
    padding: 40px 0 100px;

    .left {
      position: relative;
      .shape {
        position: absolute;
        position: absolute;
        bottom: 90px;
        width: 70px;
        height: 90px;
        left: -38px;
      }
      .office-img__wrapper {
        position: relative;
        img {
          box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        }
        .office-img1 {
          height: 400px;
        }
        .office-img2 {
          position: absolute;
          right: 50px;
          top: 140px;
          border: 4px solid #fff;
          border-radius: 4px;
          height: 370px;
        }
      }
    }

    .right {
      padding: 60px;
      h1 {
        padding-right: 70px;
        @extend .title;
      }
      p {
        margin-top: 18px;
        @extend .text;
      }
    }
  }

  .habits {
    margin-right: 100px;
    background: #f4f4f4;
    padding: 80px;
    margin-bottom: 120px;

    .left {
      padding-right: 100px;
      h1 {
        @extend .title;
      }
      p {
        padding: 0;
        @extend .text;
      }
      ul {
        list-style-type: none;
        column-count: 2;
        padding-top: 20px;

        li {
          padding-bottom: 6px;
          font-size: 16px;
          @extend .text;
          img {
            padding-right: 10px;
          }
        }
      }
    }

    .right {
      position: relative;
      .habit-shape {
        position: absolute;
        top: 493px;
        right: 150px;
        width: 90px;
        height: 70px;
      }
      position: relative;
      .habit-img {
        position: absolute;
        border-radius: 4px;
        box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
      }
    }
  }

  .magic {
    margin: 80px 0 140px;
    padding: 40px 0;

    .left {
      padding-right: 120px;
      padding-top: 80px;
      h1 {
        @extend .title;
      }
      p {
        @extend .text;
      }
      .buttons {
        display: flex;
        justify-content: flex-start;

        a {
          @extend .button;
        }

        .how-works {
          background: #175cff;
          color: #fff;
          margin-right: 16px;
        }
        .our-blog {
          color: #175cff;
          border: 2px solid #e5e5e5;
          padding: 15px 40px;
        }
      }
    }

    .right {
      position: relative;

      .shape1 {
        position: absolute;
        top: 431px;
        width: 70px;
        height: 90px;
        left: 26px;
      }
      .shape2 {
        position: absolute;
        top: 80px;
        width: 70px;
        height: 90px;
        right: -38px;
      }
      .magic-img__wrapper {
        position: relative;
        .magic-img1 {
          position: absolute;
          left: 50px;
          top: 128px;
          border: 4px solid #fff;
          border-radius: 4px;
          height: 370px;
        }
        .magic-img2 {
          height: 400px;
          float: right;
        }
        img {
          box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        }
      }
    }
  }
}
</style>
