<template>
  <footer :absolute="!fixed">
    <v-container>
      <div class="footer-main">
        <v-row>
          <v-col md="4">
            <div class="logo">
              <img src="../assets/images/logo.svg" alt="logo" />
              <h1>Master Flow</h1>
            </div>
            <div class="number">+1 (2345) 678-90-12</div>
            <div class="support">support@master.com</div>
          </v-col>
          <v-col md="4">
            <h4 class="menu">Menu</h4>
            <ul class="menu-items">
              <nuxt-link v-for="item in items" :key="item.title" :to="item.to">
                {{ item.title }}
              </nuxt-link>
            </ul>
          </v-col>
          <v-col md="4">
            <h4 class="menu">Socials</h4>
            <ul class="menu-items">
              <li>
                <a href="#">Facebook</a>
              </li>
              <li>
                <a href="#">Twitter</a>
              </li>
              <li>
                <a href="#">Instagram</a>
              </li>
              <li>
                <a href="#">Linkedin</a>
              </li>
            </ul>
          </v-col>
        </v-row>
      </div>
      <div class="footer-bottom">
        <div class="social-logos">
          <a
            v-for="icon in socialIcons"
            :key="icon.name"
            href="#"
            :class="icon.name"
            ><img :src="icon.img" :alt="icon.name"
          /></a>
        </div>
        <div class="rights">&copy; 2020 Master. All right reserved.</div>
      </div>
    </v-container>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      fixed: false,
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
      ]
    };
  },
  props: {
    socialIcons: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="scss">
footer {
  padding: 40px 0 20px;
  background: #17154b !important;
  .footer-main {
    padding-bottom: 30px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.8);
    .logo {
      margin-bottom: 16px;

      h1 {
        font-family: Gilroy;
        font-style: normal;
        font-weight: 600;
        font-size: 22px;
        line-height: 26px;
        display: inline;
        margin-left: 8px;
        color: #ffffff;
      }
    }
    .number {
      color: #fff;
      font-size: 16px;
      @extend .text;
    }
    .support {
      color: #fff;
      font-size: 14px;
      @extend .text;
    }

    .menu {
      text-transform: uppercase;
      color: #fff;
      margin-bottom: 10px;
      @extend .text;
    }
    .menu-items {
      list-style-type: none;
      padding: 0;
      column-count: 2;

      a {
        text-decoration: none;
        display: block;
        color: #fff;
        font-size: 14px;
        cursor: pointer;
        @extend .text;

        &::before {
          background: none !important;
        }
      }
    }
  }
  .footer-bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 30px;
    .social-logos {
      a {
        border-radius: 50%;
        border: 1px solid #e5e5e5;
        margin-right: 6px;
      }
      .fb {
        padding: 12px 15px 8px;
      }
      .twitter,
      .instagram {
        padding: 12px 11px 8px;
      }
    }
    .rights {
      color: #fff;
      font-size: 14px;
      @extend .text;
    }
  }
}
</style>
