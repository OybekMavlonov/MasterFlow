<template>
  <v-app light>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <div class="top">
        <router-link to="/">
          <div class="logo d-flex justify-center">
            <img src="../assets/images/logo.svg" alt="logo" />
            <h1>Master Flow</h1>
          </div>
        </router-link>
      </div>
      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          router
          :to="item.link"
          link
        >
          <v-list-item-content>
            <v-list-item-title class="nav-link">{{
              item.title
            }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <div class="social-icons d-flex justify-center">
        <a href="#" class="vk">
          <!-- <img src="./assets/svg/vk.svg" /> -->
        </a>
        <a href="#" class="fb">
          <!-- <img src="./assets/svg/facebook.svg" /> -->
        </a>
        <a href="#" class="instagram">
          <!-- <img src="./assets/svg/instagram.svg" /> -->
        </a>
      </div>
    </v-navigation-drawer>

    <v-app-bar app color="#fff" fixed>
      <v-container>
        <v-row>
          <v-app-bar-nav-icon
            @click.stop="drawer = !drawer"
            class="hidden-sm-and-up"
          ></v-app-bar-nav-icon>
          <div class="logo">
            <img src="../assets/images/logo.svg" alt="logo" />
            <h1>Master Flow</h1>
          </div>
          <v-spacer></v-spacer>
          <div class="nav">
            <v-btn
              text
              v-for="item in items"
              :key="item.title"
              router
              :to="item.to"
              class="hidden-xs-only"
            >
              {{ item.title }}
            </v-btn>
          </div>
          <v-spacer></v-spacer>
          <div class="loginarea hidden-xs-only">
            <v-btn text class="enter">
              <span class="mr-2">Log in</span>
            </v-btn>
            <a href="#">Get Started</a>
          </div>
        </v-row>
      </v-container>
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      items: [
        {
          title: "Home",
          to: "/"
        },
        {
          title: "Pricing",
          to: "/pricing"
        },
        {
          title: "Services",
          to: "/services"
        },
        {
          title: "Blog",
          to: "/blog"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js"
    };
  }
};
</script>

<style lang="scss">
a {
  text-decoration: none;
}
header {
  height: 90px !important;
  box-shadow: none !important;
  @include for-phone-only {
    height: 70px !important;
  }
  @media (max-width: 480px) {
    height: 60px !important;
  }
  .v-toolbar__content {
    height: 90px !important;
    padding: 15px 16px;
    @include for-phone-only {
      height: 70px !important;
    }
    @media (max-width: 480px) {
      height: 60px !important;
    }
    .row {
      @include for-tablet-landscape-up {
        justify-content: space-between;
      }
    }
  }
  .logo {
    display: flex;
    align-items: center;
    justify-content: space-between;
    h1 {
      font-family: Gilroy;
      font-style: normal;
      font-weight: 600;
      font-size: 26px;
      line-height: 31px;
      color: #0a083b;
      margin-left: 12px;
      @include for-tablet-portrait-up {
        margin-right: 2px;
        font-size: 22px;
      }
    }
  }
  .spacer {
    @include for-tablet-portrait-up {
      display: none;
    }
  }
  .v-btn {
    text-transform: capitalize;
    padding: 0 22px !important;
    font-family: "Gilroy";
    font-size: 16px;
    font-style: normal;
    font-weight: 500 !important;
    line-height: 19px;
    letter-spacing: 0px;
    text-align: center;
    color: #57586e !important;
    &:before {
      background: none !important;
    }
    @include for-tablet-portrait-up {
      padding: 0 10px !important;
    }
    @media (max-width: 640px) {
      padding: 0px 2px !important;
    }
  }
  .v-btn--active {
    color: #0a083b !important;
    font-weight: 600 !important;
  }
  .loginarea {
    a {
      display: inline;
      color: #175cff;
      border: 1.4px solid #e5e5e5;
      box-sizing: border-box;
      @extend .button;
    }
  }
}

.v-navigation-drawer__content {
  .top {
    padding: 16px;

    a {
      .logo {
        h1 {
          font-family: Gilroy;
          font-style: normal;
          font-weight: 600;
          font-size: 22px;
          line-height: 31px;
          color: #0a083b;
          margin-left: 6px;
        }
      }
    }
  }
}
.v-main {
  padding: 90px 0px 0px !important;
}
</style>
