<template>
  <div class="blog-wrapper">
    <div class="blog-main">
      <v-container>
        <v-row>
          <v-col cols="12" sm="12" md="6">
            <div class="left">
              <div class="bg">
                <img
                  class="home-img"
                  src="../assets/images/home-img.png"
                  alt=""
                />
              </div>
            </div>
          </v-col>
          <v-col cols="12" sm="12" md="6">
            <div class="right">
              <h1>Your business in one platform.</h1>
              <p>
                Read our latest articles with ease. They explain how we get
                there together with your goal of your company or startup. Always
                new content. This is Master Flow.
              </p>
              <div class="buttons">
                <div class="search-field">
                  <img src="../assets/images/search.png" alt="search" />
                  <input
                    type="text"
                    class="search-article"
                    placeholder="Search article..."
                    v-model="search"
                  />
                </div>
                <button href="#" class="started">
                  Search
                </button>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <Subscribe :title="blogTitle" :button="blogButton"></Subscribe>

    <Articles :searchedArticle="searchedArticle"></Articles>

    <div class="newsletter">
      <v-container>
        <div class="blue-text">newsletter</div>
        <div class="newsletter-inside">
          <!-- <v-row> -->
          <!-- <v-col md="6"> -->
          <h1>To not miss any article, subscribe to our newsletter!</h1>
          <!-- </v-col> -->
          <!-- <v-col md="6"> -->
          <button class="subscribe-button">Subscribe</button>
          <!-- </v-col> -->
          <!-- </v-row> -->
        </div>
      </v-container>
    </div>

    <Footer :socialIcons="socialIcons"></Footer>
  </div>
</template>

<script>
import Subscribe from "~/components/Subscribe.vue";
import Articles from "~/components/Articles.vue";
import Footer from "~/components/Footer.vue";
import { mapActions } from "vuex";
import { articles } from "../articles.js";

export default {
  data() {
    return {
      blogTitle: "Receive our articles by mail!",
      blogButton: "Submit",
      search: "",
      articles: articles,
      socialIcons: [
        { name: "fb", img: require("../assets/images/facebook.png") },
        { name: "twitter", img: require("../assets/images/twitter.png") },
        { name: "instagram", img: require("../assets/images/instagram.png") }
      ]
    };
  },
  components: {
    Subscribe,
    Articles,
    Footer
  },
  computed: {
    searchedArticle() {
      return this.articles.filter(article => {
        return article.title.toLowerCase().match(this.search.toLowerCase());
      });
    }
  }
};
</script>

<style lang="scss">
.blog-wrapper {
  padding: 30px 0 0;
  .blog-main {
    .left {
      position: relative;

      .bg {
        width: 500px;
        height: 500px;
        transform: translate(-50px, 40px);
        background: #17154b;
        border-radius: 0px;
        position: relative;
        @include for-desktop-up {
          width: 440px;
          height: 470px;
        }
        @include for-tablet-landscape-up {
          width: 70%;
          transform: translate(110px, 40px);
        }
        @include for-phone-only {
          transform: translate(60px, 20px);
          height: 380px;
        }

        .home-img {
          width: 500px;
          height: 500px;
          transform: translate(40px, -40px);
          border-radius: 4px;
          box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.06);

          @include for-desktop-up {
            width: 440px;
            height: 470px;
          }
          @include for-tablet-landscape-up {
            width: 100%;
          }
          @include for-phone-only {
          height: 380px;
        }
        }
      }
    }
    .right {
      padding: 100px 48px 150px 48px;
      @include for-desktop-up {
        padding: 100px 10px 140px 30px;
      }
      @include for-tablet-landscape-up {
        padding: 30px 80px;
        text-align: center;
      }
      @include for-tablet-portrait-up {
        padding: 30px 80px 0px;
      }
      @include for-phone-only {
          padding: 20px 50px 0;
        }
      h1 {
        font-size: 52px;
        line-height: 62px;
        @extend .title;
        @include for-tablet-portrait-up {
          font-size: 40px;
          line-height: 50px;
        }
        @include for-phone-only {
          font-size: 28px;
          line-height: 38px;
        }
      }
      p {
        line-height: 26px;
        margin: 18px 0 26px;
        @extend .text;
        @include for-tablet-portrait-up {
          margin: 14px 0 20px;
        }
        @include for-phone-only {
          margin: 6px 0 14px;
        }
      }
      .buttons {
        display: flex;
        justify-content: flex-start;
        @include for-tablet-landscape-up {
          justify-content: center;
        }
        button {
          @extend .button;
        }
        .started {
          background: #175cff;
          color: #fff;
          padding: 16px 50px;
          @include for-tablet-portrait-up {
            padding: 10px 30px !important;
          }
        }
        .search-field {
          position: relative;
          margin-right: 12px;
          .search-article {
            width: 290px;
            border: 2px solid rgb(229, 229, 229);
            border-radius: 30px;
            padding: 14px 0 14px 45px;
            font-family: Gilroy;
            font-style: normal;
            font-weight: 500;
            font-size: 17px;
            line-height: 20px;
            display: flex;
            align-items: center;
            color: #57586e;
            opacity: 0.5;

            &:focus {
              outline: none;
            }
          }
          img {
            position: absolute;
            top: 19px;
            left: 20px;
          }
        }
      }
    }
  }

  .subscribe {
    margin-bottom: 50px;
    .newsletter-wrapper {
      .newsletter-background {
        display: none;
      }
      .newsletter {
        background: #f4f4f4;
        .subscribe-shape {
          display: none;
        }
        h1 {
          color: #0a083b;
        }
        p {
          color: #57586e;
        }
      }
    }
  }

  .newsletter {
    background: #17154b;
    padding: 50px 0 0;
    @include for-tablet-landscape-up {
          padding-top: 20px;
        }
    .blue-text {
      color: #fff;
    }

    &-inside {
      border-bottom: 1px solid rgba(255, 255, 255, 0.8);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-bottom: 55px;
       @include for-tablet-landscape-up {
          padding-bottom: 30px;
        }

      h1 {
        width: 50%;
        color: #fff;
        @extend .title;
      }
      .subscribe-button {
        background: #175cff;
        color: #fff;
        @extend .button;
      }
    }
  }
}
</style>
