<template>
  <div class="subscribe">
    <v-container>
      <div class="newsletter-wrapper">
        <div class="newsletter-background"></div>
        <div class="newsletter">
          <img
            src="../assets/images/subscribeShape.png"
            class="subscribe-shape"
            alt="subscribeShape"
          />
          <h1>{{ title }}</h1>
          <p>Enter your email into form below to get updates from us</p>
          <div class="input-field">
            <img src="../assets/images/mail.png" alt="mail" />
            <input type="email" placeholder="Write your email..." />
            <button>{{ button }}</button>
          </div>
        </div>
      </div>
    </v-container>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    button: {
      type: String,
      required: true
    }
  }
};
</script>

<style lang="scss">
.subscribe {
  margin: 50px 0 100px;
  .newsletter-wrapper {
    position: relative;
    .newsletter-background {
      position: absolute;
      top: 40px;
      right: -40px;
      background: #f4f4f4;
      width: 1161px;
      height: 339px;
    }

    .newsletter {
      background: #175cff;
      border-radius: 4px;
      text-align: center;
      padding: 90px 0;
      position: relative;

      .subscribe-shape {
        position: absolute;
        top: -37px;
        right: 240px;
        width: 90px;
      }

      h1 {
        color: #fff;
        @extend .title;
      }
      p {
        color: #fff;
        @extend .text;
      }

      .input-field {
        display: inline;
        position: relative;
        border-radius: 4px;
        padding: 19px 0px;
        background: #fff;

        input {
          width: 410px;
          background: #fff;
          padding: 16px 120px 16px 40px;
          border-radius: 4px;
          font-family: Gilroy;
          font-style: normal;
          font-weight: 500;
          font-size: 16px;
          line-height: 19px;
          color: #959ead;
          &:focus {
            outline: none;
          }

          &::-webkit-input-placeholder {
            /* Edge */
            font-family: Gilroy;
            color: #959ead;
            font-style: normal;
            font-weight: 500;
            font-size: 16px;
            line-height: 19px;
          }

          &:-ms-input-placeholder {
            /* Internet Explorer 10-11 */
            font-family: Gilroy;
            color: #959ead;
            font-style: normal;
            font-weight: 500;
            font-size: 16px;
            line-height: 19px;
          }

          &::placeholder {
            font-family: Gilroy;
            font-style: normal;
            color: #959ead;
            font-weight: 500;
            font-size: 16px;
            line-height: 19px;
          }
        }
        img {
          position: absolute;
          top: 20px;
          left: 14px;
        }
        button {
          position: absolute;
          top: 7px;
          right: 8px;
          padding: 12px 22px;
          background: #175cff;
          border-radius: 4px;
          color: #fff;
          line-height: 20px;
          @extend .text;

          &:focus {
            outline: none;
          }
        }
      }
    }
  }
}
</style>
