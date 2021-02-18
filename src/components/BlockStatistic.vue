<template>
  <div class="blockStat">
    <div class="stat">
      <div class="row statistic">
          <div class="col-md-6 col-12">
              <div>
                <img :src="`${options.image}`" class="desktop">
              </div>
              <div>
                <img :src="`${options.imageMobile}`" class="mobile">
              </div>
          </div>
          <div class="col-md-6 col-12 txt">
            <div class="title">{{options.title}}</div>
            <div class="text">
              <div class="span-item">
                <span class="number">01.</span>
                <span class="span-text">Submit your requirements</span>
              </div>
              <div class="span-item">
                <span class="number">02.</span>
                <span class="span-text">We ﬁnd & analyze the vendors</span>
              </div>
              <div class="span-item">
                <span class="number">03.</span>
                <span class="span-text">You get the report to make a <b>decision</b></span>
              </div>
              <div class="span-item">
                <span class="number">04.</span>
                <span class="span-text">Success</span>
              </div>
            </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlockStat',
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
.statistic{
  display: flex;
  flex-wrap: wrap;
}
.stat{
  padding-top: 150px;
  margin: 0 4vw;
}
.desktop{
  width: 100%;
}
.mobile{
  display: none;
}
.title{
  font-family: Poppins;
  font-style: normal;
  font-weight: 600;
  font-size: 36px;
  line-height: 124.5%;
  /* identical to box height, or 45px */

  /* Sub title_color */

  color: #333333;
  display: flex;
  float: left;
  padding-bottom: 30px;
}
.text{
  text-align: start;
}
.txt{
  display: flex;
  flex-direction: column;
  padding-top: 2.5%;
  padding-left: 100px;
}
.number{
  font-family: Poppins;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 145.59%;
  /* or 20px */

  letter-spacing: -0.01em;

  color: #000000;
  padding-right: 19px;
}
.span-text{
  font-family: Poppins;
  font-style: normal;
  font-weight: 300;
  font-size: 28px;
  line-height: 140%;
  /* or 39px */

  /* Blue_color */

  color: #0556E2;
}
.span-item{
  margin-bottom: 14px;
}
b{
  font-weight: 300;
}
@media screen and (max-width: 769px){
  .statistic{
    display: flex;
    flex-wrap: wrap-reverse;
    margin: 0 3vw
  }
  .stat{
    padding-top: 75px;
  }
  .desktop{
    display: none;
  }
  .mobile{
    display: block;
    width: 100%;
  }
  .title{
    display: block;
    text-align: center;
    font-size: 22px;
  }
  .text{
    text-align: left;
  }
  .txt{
    padding-top: 0;
    padding-left: 0;
  }
  .span-item{
    margin-bottom: 14px;
  }
  .number{
    font-family: Poppins;
    font-style: normal;
    font-weight: normal;
    font-size: 11.5204px;
    line-height: 145.59%;
    /* or 17px */

    letter-spacing: -0.01em;

    color: #000000;
  }
  .span-text{
    font-family: Poppins;
    font-style: normal;
    font-weight: 300;
    font-size: 18px;
    line-height: 140%;
    /* or 25px */

    /* Blue_color */

    color: #0556E2;
  }
  b{
    margin-left: 2.1rem;
  }
}
@media screen and (max-width: 282px){
  .statistic{
    margin: 0 3vw;
  }
}
</style>
