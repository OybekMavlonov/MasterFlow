<template>
  <div class="experiences">
    <v-container>
      <h1>Our latest experiences</h1>
      <v-row>
        <v-col
          cols="12"
          sm="6"
          md="4"
          v-for="item in experience"
          :key="item.category"
        >
          <div class="experiences-item">
            <img :src="item.img" class="exp1" alt="exp1" />
            <span>{{ item.category }}</span>
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
        },
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.experiences {
  padding: 50px 0;

  h1 {
    margin-bottom: 40px;
    @extend .title;
  }
  .col-md-4:first-child {
    .experiences-item {
      &::after {
        content: url("../assets/images/pricingShape.png");
        position: absolute;
        width: 70px;
        height: 90px;
        left: -25px;
        top: 130px;
      }
    }
  }
  &-item {
    &:first-child {
      position: relative;
    }
    img {
      border-radius: 4px;
      box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.04);
    }
    .exp1 {
      position: relative;
    }
    span {
      color: #57586e;
      font-family: Gilroy;
      font-style: normal;
      font-weight: 600;
      font-size: 14px;
      line-height: 20px;
    }
    h4 {
      font-family: Gilroy;
      font-style: normal;
      font-weight: 600;
      font-size: 18px;
      line-height: 28px;
      color: #0a083b;
      margin-bottom: 24px;
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
