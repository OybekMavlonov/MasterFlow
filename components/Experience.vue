<template>
  <div class="experiences">
    <v-container>
      <h1>Our latest experiences</h1>
      <v-row>
        <v-col
          cols="12"
          sm="4"
          md="4"
          v-for="item in experience"
          :key="item.category"
        >
          <div class="experiences-item">
            <img :src="item.img" class="exp1" alt="exp1" />
            <div class="category">{{ item.category }}</div>
            <h4>{{ item.info }}</h4>
            <a href="#" class="read-more">Read more</a>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      experience: [
        {
          img: require("../assets/images/exp1.png"),
          category: "Products",
          info: "All our physical products that we have branded and sold"
        },
        {
          img: require("../assets/images/exp2.png"),
          category: "Marketing",
          info: "Our statistics in our latest developed ecommerce"
        },
        {
          img: require("../assets/images/exp3.png"),
          category: "Wireframe",
          info: "The strategy we use to reach your goal quickly"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.experiences {
  padding: 50px 0;
  @media (max-width: 550px) {
    padding: 20px 0;
  }

  h1 {
    margin-bottom: 40px;
    @extend .title;
    @include for-phone-only {
      padding: 0px 40px;
      margin-bottom: 20px;
    }
  }
  .col-md-4:first-child {
    .experiences-item {
      &::after {
        content: "";
        background-image: url("../assets/images/pricingShape.png");
        position: absolute;
        width: 70px;
        height: 90px;
        left: -25px;
        top: 130px;
        @include for-desktop-up {
          background-size: 25px 60px;
          top: 90px;
        }
        @include for-tablet-landscape-up {
          display: none;
        }
      }
    }
  }
  &-item {
    @include for-phone-only {
      padding: 0px 40px;
    }
    &:first-child {
      position: relative;
    }
    img {
      border-radius: 4px;
      box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.04);
      @include for-desktop-up {
        width: 270px;
      }
      @include for-tablet-portrait-up {
        width: 220px;
      }
      @media (max-width: 700px) {
        width: 200px;
      }
      @include for-phone-only {
        width: 100%;
      }
    }
    .exp1 {
      position: relative;
    }
    .category {
      color: #57586e;
      font-family: Gilroy;
      font-style: normal;
      font-weight: 600;
      font-size: 14px;
      line-height: 20px;
      @include for-phone-only {
        font-size: 16px;
        line-height: 18px;
        margin-bottom: 4px;
      }
    }
    h4 {
      font-family: Gilroy;
      font-style: normal;
      font-weight: 600;
      font-size: 18px;
      line-height: 28px;
      color: #0a083b;
      margin-bottom: 24px;

      @include for-tablet-landscape-up {
        font-size: 16px;
        line-height: 24px;
        margin-bottom: 12px;

        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
      }
      @include for-phone-only {
        font-size: 18px;
        line-height: 24px;
        margin-bottom: 10px;
      }
    }
    .read-more {
      font-family: Gilroy;
      font-style: normal;
      font-weight: bold;
      font-size: 14px;
      line-height: 20px;
      text-transform: uppercase;
      letter-spacing: 2px;
      color: #175cff;
      text-decoration: none;
    }
  }
}
</style>
