<template>
  <div class="wrapper">
    <div class="home-main">
      <v-container>
        <v-row>
          <v-col cols="12" sm="12" md="6">
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
          <v-col cols="12" sm="12" md="6">
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
            <v-col cols="12" sm="6" md="6">
              <div class="left">
                <h1>We have worked with them. Our super customers.</h1>
              </div>
            </v-col>
            <v-col cols="12" sm="6" md="6">
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
            <v-row>
              <v-col v-for="(logo, index) in brandLogo" :key="index">
                <img :src="logo" alt="brandlogo" />
              </v-col>
            </v-row>
          </div>
        </div>
      </v-container>
    </div>

    <div class="office">
      <v-container>
        <v-row>
          <v-col cols="12" sm="6" md="6">
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
          <v-col cols="12" sm="6" md="6">
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
          <v-col cols="12" sm="6" md="6">
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
          <v-col cols="12" sm="6" md="6">
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
          <v-col cols="12" sm="12" md="6">
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
          <v-col cols="12" sm="12" md="6">
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
      @include for-desktop-up {
        padding: 130px 80px 130px 0;
      }
      @include for-tablet-landscape-up {
        padding: 40px 0 20px;
        text-align: center;
      }
      @include for-phone-only {
        padding: 20px 0;
      }
      .welcome {
        @extend .blue-text;
      }
      h1 {
        font-size: 52px;
        line-height: 62px;
        @extend .title;

        @include for-desktop-up {
          font-size: 44px;
          line-height: 54px;
        }
        @include for-tablet-portrait-up {
          font-size: 38px;
          line-height: 44px;
        }
        @media (max-width: 500px) {
          font-size: 28px;
          line-height: 28px;
        }
      }
      p {
        line-height: 26px;
        margin: 18px 0 26px;
        @extend .text;
        @include for-desktop-up {
          margin: 10px 0 18px;
        }
        @include for-tablet-landscape-up {
          padding: 0 60px;
        }
        @include for-phone-only {
          font-size: 16px;
        }
        @media (max-width: 500px) {
          font-size: 14px;
          line-height: 20px;
          padding: 0;
        }
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
        @include for-tablet-landscape-up {
          justify-content: center;
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
        @include for-desktop-up {
          width: 60px;
          height: 70px;
          left: -20px;
        }
        @media (max-width: 1090px) {
          left: -36px;
        }
        @include for-tablet-landscape-up {
          left: 60px;
        }
        @include for-tablet-portrait-up {
          left: 38px;
        }
        @include for-phone-only {
          left: 9px;
          bottom: 60px;
        }
        @media (max-width: 700px) {
          display: none;
        }
      }

      .bg {
        width: 500px;
        height: 590px;
        transform: translate(124px, -12px);
        background: #17154b;
        border-radius: 0px;
        position: relative;
        @include for-desktop-up {
          width: 480px;
          height: 570px;
          transform: translate(50px, -12px);
        }
        @media (max-width: 1090px) {
          width: 460px;
          transform: translate(30px, -12px);
        }
        @include for-tablet-landscape-up {
          width: 650px;
          height: 530px;
          transform: translate(140px, -12px);
        }
        @media (max-width: 860px) {
          transform: translate(110px, -12px);
        }
        @include for-tablet-portrait-up {
          width: 560px;
          height: 460px;
        }
        @media (max-width: 700px) {
          transform: translate(70px, -12px);
        }
        @media (max-width: 700px) {
          transform: translate(50px, -12px);
        }
        @include for-phone-only {
          width: 460px;
          height: 400px;
          transform: translate(70px, -12px);
        }
        @media (max-width: 550px) {
          width: 400px;
          height: 360px;
        }
        @media (max-width: 500px) {
          width: 330px;
          height: 280px;
          transform: translate(80px, -12px);
        }
        @media (max-width: 430px) {
          width: 280px;
          height: 250px;
        }
        @media (max-width: 370px) {
          transform: translate(50px, -12px);
        }
        @media (max-width: 345px) {
          width: 240px;
          height: 220px;
          transform: translate(50px, -12px);
        }
        button {
          position: absolute;
          top: 53%;
          z-index: 9;
          left: 32%;
          padding: 20px 22px 14px 27px;
          background: #fff;
          border-radius: 50%;
          box-shadow: 0px 4px 12px 0px #000000 10%;
          @include for-tablet-landscape-up {
            padding: 16px 18px 10px 22px;
            left: 40%;
          }
          @media (max-width: 500px) {
            padding: 5px 10px 4px 12px;
          }
          @media (max-width: 430px) {
            padding: 3px 7px 2px 9px;
          }
          @media (max-width: 345px) {
            padding: 0px 5px 0 7px;
          }
          &:focus {
            outline: none;
          }
          img {
            @media (max-width: 500px) {
              width: 14px;
              height: 16px;
            }
            @media (max-width: 500px) {
              width: 10px;
              height: 12px;
            }
            @media (max-width: 345px) {
              width: 7px;
              height: 7px;
            }
          }
        }

        .home-img {
          width: 500px;
          height: 590px;
          transform: translate(-45px, 40px);
          border-radius: 4px;
          box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
          @include for-desktop-up {
            width: 480px;
            height: 570px;
            transform: translate(-40px, 35px);
          }
          @media (max-width: 1090px) {
            width: 460px;
            transform: translate(-35px, 35px);
          }
          @include for-tablet-landscape-up {
            width: 650px;
            height: 530px;
            transform: translate(-40px, 40px);
          }
          @include for-tablet-portrait-up {
            width: 560px;
            height: 460px;
          }
          @include for-phone-only {
            width: 460px;
            height: 400px;
          }
          @media (max-width: 550px) {
            width: 400px;
            transform: translate(-30px, 30px);
            height: 360px;
          }
          @media (max-width: 500px) {
            width: 330px;
            height: 280px;
          }
          @media (max-width: 430px) {
            width: 280px;
            height: 250px;
            transform: translate(-20px, 20px);
          }
          @media (max-width: 345px) {
            width: 240px;
            height: 220px;
          }
        }
      }
    }
  }

  .customers {
    @include for-phone-only {
      text-align: center;
    }
    &-wrapper {
      padding: 100px 0;
      border-bottom: 1px solid rgba(0, 0, 0, 0.08);
      @include for-tablet-landscape-up {
        padding: 70px 0 50px;
      }
      @include for-tablet-portrait-up {
        padding: 40px 0;
      }
      @media (max-width: 550px) {
        padding: 20px 0;
      }
      .left {
        h1 {
          @extend .title;
        }
      }
      .right {
        p {
          padding: 10px 0 10px 10px;
          @extend .text;
          @include for-tablet-portrait-up {
            padding: 0;
          }
          @media (max-width: 500px) {
            margin: -10px 0 0;
          }
        }
      }
      .customers-logo {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 40px;
        @media (max-width: 550px) {
          margin-top: 20px;
        }
      }
    }
  }

  .office {
    padding: 40px 0 100px;
    @include for-desktop-up {
      padding: 40px 0 60px;
      margin-bottom: 40px;
    }
    @include for-phone-only {
      padding: 30px 0 0;
    }
    @media (max-width: 550px) {
      padding-top: 10px;
      margin-bottom: 10px;
    }

    .left {
      position: relative;
      .shape {
        position: absolute;
        position: absolute;
        bottom: 90px;
        width: 70px;
        height: 90px;
        left: -38px;
        @include for-tablet-landscape-up {
          width: 60px;
          height: 70px;
          left: 8px;
          bottom: 80px;
        }
        @media (max-width: 480px) {
          width: 30px;
          height: 40px;
          left: 24px;
          bottom: 90px;
        }
        @media (max-width: 380px) {
          display: none;
        }
      }
      .office-img__wrapper {
        position: relative;
        img {
          box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        }
        .office-img1 {
          height: 400px;
          @include for-tablet-landscape-up {
            height: 350px;
            margin-left: 40px;
          }
          @include for-tablet-portrait-up {
            height: 320px;
          }
          @include for-phone-only {
            width: 350px;
          }
          @media (max-width: 550px) {
            width: 300px;
            height: 270px;
          }
          @media (max-width: 480px) {
            width: 250px;
            height: 240px;
          }
          @media (max-width: 480px) {
            width: 200px;
            height: 180px;
          }
          @media (max-width: 380px) {
            width: 280px;
            margin-left: 20px;
          }
        }
        .office-img2 {
          position: absolute;
          right: 50px;
          top: 140px;
          border: 4px solid #fff;
          border-radius: 4px;
          height: 370px;
          @include for-tablet-landscape-up {
            height: 320px;
            top: 130px;
            right: 0;
          }
          @include for-tablet-portrait-up {
            height: 260px;
          }
          @include for-phone-only {
            width: 330px;
          }
          @media (max-width: 550px) {
            width: 300px;
            height: 270px;
            top: 100px;
            right: 20px;
          }
          @media (max-width: 480px) {
            width: 220px;
            height: 200px;
            right: 50px;
            top: 70px;
          }
          @media (max-width: 420px) {
            width: 200px;
            height: 180px;
            top: 50px;
          }
          @media (max-width: 380px) {
            position: unset;
            width: 280px;
            margin-left: 20px;
          }
        }
      }
    }

    .right {
      padding: 60px;
      @include for-desktop-up {
        padding: 20px;
      }
      @include for-phone-only {
        padding: 60px 20px 20px 20px;
        text-align: center;
      }
      @media (max-width: 550px) {
        padding: 100px 20px 0;
      }
      @media (max-width: 420px) {
        padding: 40px 20px 0;
      }
      @media (max-width: 380px) {
        padding: 00px 20px 0;
      }
      h1 {
        padding-right: 70px;
        @extend .title;
        @media (max-width: 420px) {
          padding: 0;
        }
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
    @include for-desktop-up {
      padding: 60px;
      margin-bottom: 80px;
      margin-right: 70px;
    }
    @media (max-width: 1030px) {
      margin-right: 50px;
      padding: 40px 40px 20px;
    }
    @include for-tablet-landscape-up {
      margin: 0;
    }
    @media (max-width: 550px) {
      padding: 20px 20px 0;
    }
    .left {
      padding-right: 100px;
      @include for-desktop-up {
        padding-right: 50px;
      }
      h1 {
        @extend .title;
        @include for-tablet-portrait-up {
          margin-bottom: 10px;
        }
      }
      p {
        padding: 0;
        @extend .text;
      }
      ul {
        list-style-type: none;
        column-count: 2;
        padding: 20px 0 0;
        @media (max-width: 1030px) {
          padding-top: 0;
        }
        @media (max-width: 860px) {
          column-count: 1;
        }
        @include for-phone-only {
          column-count: 2;
        }

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

        @media (max-width: 1030px) {
          top: 422px;
        }
        @include for-tablet-landscape-up {
          width: 70px;
          height: 60px;
          top: 400px;
          right: 100px;
        }
        @media (max-width: 860px) {
          display: none;
        }
      }
      position: relative;
      .habit-img {
        position: absolute;
        border-radius: 4px;
        box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        @media (max-width: 1030px) {
          width: 380px;
        }
        @include for-tablet-landscape-up {
          height: 430px;
        }
        @media (max-width: 860px) {
          width: 340px;
          height: 450px;
          position: unset;
        }
        @include for-tablet-portrait-up {
          height: 400px;
          width: 320px;
        }
        @media (max-width: 700px) {
          width: 300px;
        }
        @media (max-width: 667px) {
          width: 280px;
        }
        @include for-phone-only {
          height: 300px;
          width: 100%;
        }
      }
    }
  }

  .magic {
    margin: 80px 0 140px;
    padding: 40px 0;

    @include for-desktop-up {
      margin: 30px 0 120px;
      padding: 20px 0;
    }
    @include for-phone-only {
      margin: 10px 0 100px;
      padding: 0;
    }

    .left {
      padding-right: 120px;
      padding-top: 80px;
      @include for-desktop-up {
        padding: 80px 20px 0 0;
      }
      @include for-tablet-landscape-up {
        padding: 10px 20px;
        text-align: center;
      }
      h1 {
        @extend .title;
      }
      p {
        @extend .text;
        @include for-tablet-landscape-up {
          padding: 0 70px;
        }
        @include for-phone-only {
          padding: 0;
        }
      }
      .buttons {
        display: flex;
        justify-content: flex-start;
        @include for-tablet-landscape-up {
          justify-content: center;
        }
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
        @include for-tablet-landscape-up {
          width: 60px;
          height: 70px;
          left: 17px;
          top: 457px;
        }
        @include for-phone-only {
          top: 250px;
        }
      }
      .shape2 {
        position: absolute;
        top: 80px;
        width: 70px;
        height: 90px;
        right: -38px;
        @include for-tablet-landscape-up {
          width: 60px;
          height: 70px;
          right: 30px;
        }
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
          @include for-tablet-landscape-up {
            width: 50%;
          }
          @include for-phone-only {
            height: 280px;
            top: 80px;
          }
        }
        .magic-img2 {
          height: 400px;
          float: right;
          @include for-tablet-landscape-up {
            width: 50%;
            margin-right: 60px;
          }
          @include for-phone-only {
            height: 280px;
          }
        }
        img {
          box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);
        }
      }
    }
  }
}
</style>
