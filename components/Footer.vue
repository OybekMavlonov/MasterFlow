<template>
  <footer :absolute="!fixed">
    <v-container>
      <div class="footer-main">
        <v-row>
          <v-col cols="12" sm="4" md="4">
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
  @media (max-width: 600px) {
    padding: 10px 0;
  }
  .footer-main {
    padding-bottom: 30px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.8);
    @media (max-width: 600px) {
      padding-bottom: 10px;
    }
    .logo {
      margin-bottom: 16px;
      @include for-phone-only {
        text-align: center;
        margin-bottom: 0;
      }
      h1 {
        font-family: Gilroy;
        font-style: normal;
        font-weight: 600;
        font-size: 22px;
        line-height: 26px;
        display: inline;
        margin-left: 8px;
        color: #ffffff;
        @include for-tablet-portrait-up {
        margin-left: 0;
      }
        
        @media (max-width: 550px) {
          font-size: 18px;
          line-height: 20px;
        }
      }
    }
    .number {
      color: #fff;
      font-size: 16px;
      @extend .text;
      @include for-phone-only {
        text-align: center;
      }
    }
    .support {
      color: #fff;
      font-size: 14px;
      @extend .text;
      @include for-phone-only {
        text-align: center;
      }
    }

    .menu {
      text-transform: uppercase;
      color: #fff;
      margin-bottom: 10px;
      @extend .text;
      @media (max-width: 550px) {
        margin-bottom: 4px;
        font-size: 14px;
      }
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
    @media (max-width: 550px) {
      margin-top: 20px;
    }
    @media (max-width: 330px) {
      display: block;
      text-align: center;
    }

    .social-logos {
      a {
        border-radius: 50%;
        border: 1px solid #e5e5e5;
        margin-right: 6px;
      }
      .fb {
        padding: 12px 15px 8px;
        @media (max-width: 400px) {
          padding: 6px 9px 3px;
        }
        img {
          @media (max-width: 400px) {
            width: 8px;
            height: 14px;
          }
        }
      }
      .twitter,
      .instagram {
        padding: 12px 11px 8px;
        @media (max-width: 400px) {
          padding: 5px 5px 3px;
        }
        img {
          @media (max-width: 400px) {
            width: 14px;
            height: 12px;
          }
        }
      }
    }
    .rights {
      color: #fff;
      font-size: 14px;
      @extend .text;
      
      @media (max-width: 330px) {
      margin-top: 10px;
    }
    }
  }
}
</style>
