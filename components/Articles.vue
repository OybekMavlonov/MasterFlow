<template>
  <div class="articles">
    <v-container>
      <v-row>
        <v-col
          cols="12"
          sm="6"
          md="4"
          v-for="item in pageList"
          :key="item.name"
        >
          <div class="articles-item">
            <img :src="item.img" class="exp1" alt="exp1" />
            <span>{{ item.category }}</span>
            <h4>{{ item.title }}</h4>
            <a href="#" class="read-more">Read more</a>
          </div>
        </v-col>
      </v-row>

      <v-pagination
        v-model="page"
        :length="Math.ceil(searchedArticle.length / 9)"
        circle
      ></v-pagination>
    </v-container>
  </div>
</template>

<script>
import { articles } from "../articles.js";
export default {
  data() {
    return {
      articles: articles,
      page: 1,
    };
  },
  props: {
    searchedArticle: {
      type: Array,
      required: true
    }
  },
  computed: {
    pageList() {
      return this.searchedArticle.slice(
        (this.page - 1) * 9,
        (this.page - 1) * 9 + 9
      );
    }
  },
  methods: {
    clickCallback(pageNum) {
      console.log(pageNum);
      this.page = pageNum;
    }
  }
};
</script>

<style lang="scss">
.articles {
  padding: 50px 0;

  &-item {
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

  .v-pagination {
    margin-top: 80px;
    position: relative;

    &__item {
      height: 42px;
      width: 42px;
      box-shadow: none;
      @extend .pagination-button;

      &:focus {
        outline: none;
      }
    }
    li {
      &:first-child,
      &:last-child {
        position: absolute;
        button {
          background: #175cff;
          height: 42px;
          width: 42px;
          box-shadow: none;
          i {
            color: #fff;
            font-size: 16px;
            @extend .pagination-button;
          }
        }
      }

      &:first-child {
        left: 0;
      }
      &:last-child {
        right: 0;
      }
    }
    .v-pagination__navigation--disabled {
      background: #f4f4f4 !important;
      i {
        color: #0a083b !important;
      }
    }
  }

  .theme--light.v-pagination .v-pagination__item {
    background: #f4f4f4;
    // color: #0a083b;
    @extend .pagination-button;
  }
}
</style>
