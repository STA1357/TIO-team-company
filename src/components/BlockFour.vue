<template>
  <div class="blockFour">
    <div class="container">
      <div class="row">
        <div class="four">
          <div class="col-md-6 col-12">
            <span>
              <img :src="`${options.image}`" class="big img-fluid">
              <img :src="`${options.imageMobile}`" class="small img-fluid">
            </span>
          </div>
          <div class="col-md-6 col-12 txt">
            <div class="title">{{options.title}}</div>
            <div class="text">{{options.text}}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockFour',
  props: {
    options: {
      type: Object,
      default () {
        return {
          title: {
            type: String,
            default: 'Space for Title'
          },
          text: {
            type: String,
            default: 'Space for Text'
          },
          image: {
            type: String,
            default: 'Space for Image'
          },
          imageMobile: {
            type: String,
            default: 'Space for Image'
          }
        }
      }
    }
  }
}
</script>

<style scoped>
  .blockFour{
    padding-top: 100px;
    background: #EBF1F9;
    padding-bottom: 100px;
  }
  .four{
    flex-wrap: wrap;
    display: flex;
  }
  .big{
    margin-left: -20%;
  }
  .small{
    display: none;
  }
  .txt{
    padding-left: 35px;
  }
  .title{
    font-family: Poppins;
    font-style: normal;
    font-weight: 600;
    font-size: 34px;
    line-height: 124.5%;
    /* or 45px */

    color: #151522;

    display: flex;
    text-align: left;
  }
  .text{
    font-family: Poppins;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 150%;
    /* or 27px */

    /* Title_color */

    color: #222222;

    display: flex;
    text-align: left;
    padding-top: 30px;
  }
  @media screen and (max-width: 769px) {
    .blockFour{
      padding-top: 50px;
      padding-bottom: 10px;
    }
    .four{
      flex-wrap: wrap-reverse;
      display: flex;
    }
    .big{
      display: none;
    }
    .small{
      display: inline-block;
      padding-bottom: 40px;
    }
    .txt{
      padding: 0;
    }
    .title{
      font-size: 22px;
      display: block;
      text-align: center;
    }
    .text{
      padding-top: 40px;
      display: block;
      text-align: center;
      font-size: 16px;
      padding-top: 0;
    }
  }
  @media screen and (max-width: 400px){
    .small{
      width: 90%;
    }
  }
</style>
