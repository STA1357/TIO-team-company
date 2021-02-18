<template>
  <div class="blockImageLeft" style="background: #EBF1F9">
    <div class="container">
      <div class="row title">
        <div class="col-md-5 col-12">
          <span class="pt-3">{{options.title}}</span>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="row wrapper" style="display: flex;">
        <div class="col-md-7 col-12">
        <span>
          <img :src="`${options.image}`" class="big img-fluid">
          <img :src="`${options.imageMobile}`" class="small img-fluid">
        </span>
        </div>

        <div class="col-md-5 col-12 pad">
            <span class="text-header pt-3">
              <img src="../assets/arrow30deg.png" alt="arrow" class="arrow">
              <span class="txt">Extend your existing team capacity</span>
            </span>
          <span class="text pt-3">Works best if you have a large project and need a tailored and experienced team to extend your existing capacity and handle
                  the work on time.</span>

          <span class="text-header pt-3">
              <img src="../assets/arrow30deg.png" alt="arrow" class="arrow">
              <span class="txt">
                Hire a software engineering team
              </span>
            </span>
          <span class="text pt-3">
              Hire a dedicated software development team if you have a speciﬁc product, app,
              or website that you’re building from scratch and need experts to get the job done.
            </span>

          <span class="text-header pt-3">
              <img src="../assets/arrow30deg.png" alt="arrow" class="arrow">
              <span class="txt">
                Find a support & maintenance team
              </span>
            </span>
          <span class="text pt-3">
              If you need to monitor, update and maintain one of your projects,
              the best option is to hire an on-demand support & maintenance team to help you.
            </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockTwo',
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
          text_header: {
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
  .blockImageLeft{
    padding-top: 100px;
    padding-bottom: 100px;
  }
  .container{
    width: auto;
  }
  .wrapper{
    flex-wrap: wrap;
  }
  .big{
    display: block;
  }
  .small{
    display: none;
  }
  .title{
    font-family: Poppins;
    font-style: normal;
    font-weight: 600;
    font-size: 31px;
    line-height: 140%;
    /* or 50px */

    /* Title_color */

    color: #222222;
    display: flex;
    text-align: left;
  }
  .text-header{
    font-family: Poppins;
    font-style: normal;
    font-weight: 300;
    font-size: 28px;
    line-height: 140%;
    /* or 39px */

    /* Blue_color */

    color: #0556E2;
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

    /* Text_color */

    color: #333333;
    display: flex;
    text-align: left;
    padding-left: 2rem;
  }
  .arrow{
    height: 75%;
    padding-right: 10px;
  }
  .pad{
    padding: 90px 2vw 0px 2vw;
  }
  @media screen and (max-width: 769px){
    .blockImageLeft{
      padding-top: 60px;
      padding-bottom: 40px;
    }
    .wrapper{
      flex-wrap: wrap-reverse;
    }
    .big{
      display: none;
    }
    .small{
      display: inline-block;
      padding-bottom: 40px;
    }
    .title{
      text-align: center;
      font-size: 24px;
    }
    .text-header{
      display: flex;
      font-size: 22px;
    }
    .text{
      text-align: left;
      display: block;
      padding-left: 0;
      font-size: 13px;
      font-weight: 500;
    }
    .pad{
      padding: 0 15vw;
    }
  }
</style>
