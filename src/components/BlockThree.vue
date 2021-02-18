<template>
  <div style="background: #F2F5F9;" class="think">
    <div class="container">
      <div class="row title">
        <div class="col-md-5 col-12 amg">
          <span>{{options.title}}</span>
        </div>
      </div>
    </div>
    <div class="container pl-2 padtop">
      <div class="row">
        <div class="col-md-5 col-12 mrg">

          <span class="text pt-4">
            <img :src="`${options.imageText}`" class="good">
            Choose from vetted engineering teams
          </span>

          <span class="text pt-4">
            <img :src="`${options.imageText}`" class="good">
            Focus on decision-making
          </span>

          <span class="text pt-4">
            <img :src="`${options.imageText}`" class="good">
            Run your business while we do the research
          </span>

          <span class="text pt-4">
            <img :src="`${options.imageText}`" class="good">
            Save time & money
          </span>
          <div class="plainDesktop">
            <img src="../assets/plainForThirdBlock.svg">
          </div>
          <div class="plainMobile">
            <img src="../assets/plainForThirdMobile.svg">
          </div>
        </div>
        <div class="col-md-7 col-12">
        <span>
          <img :src="`${options.image}`" class="big img-fluid">
          <img :src="`${options.imageMobile}`" class="small img-fluid">
        </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Block',
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
          imageText: {
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
  .container{
    width: auto;
  }
  .think{
    padding-top: 100px;
    padding-bottom: 100px;
  }
  .big{
    display: block;
    margin-top: -100px;
  }
  .small{
    display: none;
  }
  .title{
    font-family: Poppins;
    font-style: normal;
    font-weight: 600;
    font-size: 36px;
    line-height: 140%;
    /* or 50px */

    /* Title_color */

    color: #222222;
    display: flex;
    text-align: left;
  }
  .text{
    font-family: Poppins;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 140%;
    /* or 39px */

    /* Sub title_color */

    color: #333333;
    display: flex;
    text-align: left;
  }
  .good{
    padding-right: 24px;
  }
  .padtop{
    padding-top: 50px;
  }
  .mrg{
    margin-top: 5%;
  }
  .amg{
    margin-bottom: -7%;
  }
  .plainDesktop{
    display: flex;
    flex-direction: row-reverse;
    padding-top: 40px;
  }
  .plainMobile{
    display: none;
  }
  @media screen and (max-width: 769px){
    .think{
      padding-top: 50px;
      padding-bottom: 0;
    }
    .big{
      display: none;
    }
    .small{
      display: inline-block;
      padding-top: 50px;
      padding-bottom: 0;
    }
    .title{
      text-align: center;
      font-size: 22px;
    }
    .text{
      display: grid;
      text-align: -webkit-center;
    }
    .good{
      padding-right: 0;
      width: 20px;
      height: 20px;
    }
    .padtop{
      padding-top: 0;
    }
    .mrg{
      margin-top: 0;
    }
    .amg{
      margin-bottom: 0;
    }
    .plainDesktop{
      display: none;
    }
    .plainMobile{
      display: flex;
      position: absolute;
      left: 0;
      transform: translateY(-115px);
    }
  }
</style>
