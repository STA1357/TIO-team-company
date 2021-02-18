<template>
  <div class="block">
    <div class="container">
      <div class="row title">
        <div class="col-md-5 col-12 pt-3">
          <span>{{options.title}}</span>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="row">
        <div class="col-md-5 col-12 pt-3">
          <span class="text">{{options.text}}</span>
          <div class="learn">
            <BlButton></BlButton>
          </div>

        </div>
        <div class="col-md-7 col-12">
        <span>
          <img :src="`${options.image}`" class="big img-fluid">
          <img :src="`${options.imageMobile}`" class="small img-fluid">
          <img :src="`${options.imagePlain}`" class="bigPlain img-fluid">
          <img :src="`${options.imagePlainMobile}`" class="smallPlain img-fluid">
        </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import BlButton from './buttons/BlueButton'
export default {
  name: 'Block',
  components: { BlButton },
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
          },
          imagePlain: {
            type: String,
            default: 'Space for Image'
          },
          imagePlainMobile: {
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
  .block{
    background: #F2F5F9;
    padding-top: 140px
  }
  .container{
    width: auto;
  }
  .big{
    display: block;
    margin-top: -30%;
  }
  .bigPlain{
    display: block;
    position: absolute;
    right: 0;
    top: 180px;
  }
  .small{
    display: none;
  }
  .smallPlain{
    display: none;
  }
  .learn{
    float: left;
    padding-top: 40px;
  }
  .title{
    font-family: Poppins;
    font-style: normal;
    font-weight: 600;
    font-size: 46px;
    line-height: 124.5%;
    /* or 70px */

    /* Text_color */

    color: #333333;
    display: flex;
    text-align: left;
  }
  .text{
    font-family: Poppins;
    font-style: normal;
    font-weight: normal;
    font-size: 16px;
    line-height: 150%;
    /* or 31px */

    /* Sub title_color */

    color: #333333;
    display: flex;
    text-align: left;
    margin-top: 24px;
  }
  @media screen and (max-width: 769px){
    .block{
      padding-top: 80px;
      margin-top: 0;
    }
    .big{
      display: none;
    }
    .bigPlain{
      display: none;
    }
    .small{
      display: inline-block;
      padding-top: 40px;
    }
    .smallPlain{
      display: block;
      position: absolute;
      right: 20px;
      top: 221px;
    }
    .learn{
      float: none;
      padding-top: 40px;
    }
    .title{
      display: contents;
      text-align: center;
      font-size: xx-large;
      padding: 50px;
    }
    .text{
      text-align: center;
      margin-top: 0;
    }
  }
  @media screen and (max-width: 359px){
    .smallPlain{
      display: block;
      position: absolute;
      right: 20px;
      top: 173px;
      width: 40%;
    }
  }
</style>
