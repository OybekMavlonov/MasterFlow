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
  @include for-desktop-up {
    margin: 10px 0 60px;
  }
  @include for-tablet-portrait-up {
    margin: 30px 0 40px;
  }
  @media (max-width: 550px) {
    margin: 0;
  }
  .newsletter-wrapper {
    position: relative;
    @include for-tablet-landscape-up {
      padding: 0 40px;
    }
    @include for-phone-only {
      padding: 0;
    }
    .newsletter-background {
      position: absolute;
      top: 40px;
      right: -40px;
      background: #f4f4f4;
      width: 1161px;
      height: 339px;
      @include for-desktop-up {
        width: 876px;
      }
      @include for-tablet-landscape-up {
        width: 836px;
        right: 0;
        top: 30px;
      }
      @media (max-width: 900px) {
        width: 780px;
      }
      @media (max-width: 850px) {
        width: 730px;
      }
      @media (max-width: 800px) {
        width: 680px;
      }
      @include for-tablet-portrait-up {
        height: 320px;
      }
      @media (max-width: 750px) {
        width: 630px;
      }
      @media (max-width: 700px) {
        width: 600px;
      }
      @media (max-width: 670px) {
        width: 550px;
      }
      @include for-phone-only {
        display: none;
      }
    }

    .newsletter {
      background: #175cff;
      border-radius: 4px;
      text-align: center;
      padding: 90px 0;
      position: relative;
      @media (max-width: 500px) {
        padding: 40px 0;
      }

      .subscribe-shape {
        position: absolute;
        top: -37px;
        right: 240px;
        width: 90px;

        @include for-tablet-landscape-up {
          right: 150px;
          width: 70px;
          top: -30px;
        }
        @include for-tablet-portrait-up {
          right: 80px;
        }
        @include for-phone-only {
          display: none;
        }
      }

      h1 {
        color: #fff;
        @extend .title;
      }
      p {
        color: #fff;
        @extend .text;
        @media (max-width: 390px) {
            padding: 0 12px;
          }
      }

      .input-field {
        display: inline;
        position: relative;
        border-radius: 4px;
        padding: 19px 0px;
        background: #fff;
        @media (max-width: 500px) {
          padding: 12px 0;
        }

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
          @media (max-width: 500px) {
            padding: 10px 80px 10px 28px;
            font-size: 14px;
            line-height: 16px;
          }
          @media (max-width: 460px) {
            width: 380px;
          }
          @media (max-width: 420px) {
            width: 350px;
          }
          @media (max-width: 390px) {
            width: 290px;
          }
          @media (max-width: 320px) {
            width: 260px;
            padding-right: 64px;
          }
          @media (max-width: 290px) {
            width: 240px;
            padding-right: 64px;
          }
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
            @media (max-width: 500px) {
              font-size: 14px;
              line-height: 16px;
            }
          }

          &:-ms-input-placeholder {
            /* Internet Explorer 10-11 */
            font-family: Gilroy;
            color: #959ead;
            font-style: normal;
            font-weight: 500;
            font-size: 16px;
            line-height: 19px;
            @media (max-width: 500px) {
              font-size: 14px;
              line-height: 16px;
            }
          }

          &::placeholder {
            font-family: Gilroy;
            font-style: normal;
            color: #959ead;
            font-weight: 500;
            font-size: 16px;
            line-height: 19px;
            @media (max-width: 500px) {
              font-size: 14px;
              line-height: 16px;
            }
          }
        }
        img {
          position: absolute;
          top: 20px;
          left: 14px;
          @media (max-width: 500px) {
            top: 14px;
            left: 8px;
          }
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
          @media (max-width: 500px) {
            padding: 8px 16px;
            top: 4px;
            right: 4px;
          }
          @media (max-width: 390px) {
            padding: 6px;
            top: 5px;
            font-size: 12px;
          }

          &:focus {
            outline: none;
          }
        }
      }
    }
  }
}
</style>
