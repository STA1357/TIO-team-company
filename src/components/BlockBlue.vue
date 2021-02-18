<template>
    <div class="blockBlue">
      <div class="container pt-3">
        <div class="row">
          <div class="col-md-3 col-12">
            <div class="plainDesktop">
              <img :src="`${options.image}`" class="bigPlain">
            </div>
            <div class="plainMobile">
              <img :src="`${options.imageMobile}`" class="smallPlain">
            </div>
          </div>
          <div class="col-md-6 col-12">
            <div>
              <span class="blue-title">{{options.title}}</span>
            </div>
            <div>
              <span class="blue-text">{{options.text}}</span>
            </div>
            <div class="pt-4">
              <YellowButton></YellowButton>
            </div>
          </div>
          <div class="col-md-3 col-12">
            <img :src="`${options.imageTwo}`" class="big">
            <img :src="`${options.imageTwoMobile}`" class="small">
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import YellowButton from './buttons/YellowButton'
export default {
  name: 'BlockBlue',
  components: { YellowButton },
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
          imageTwo: {
            type: String,
            default: 'Space for Image'
          },
          imageTwoMobile: {
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
.blockBlue{
  background: #0660FC;
  color: white;
  padding-top: 80px;
}
.big{
  margin-top: 50px;
}
.small{
  display: none;
}
.bigPlain{
  display: block;
  position: absolute;
  left: -80%;
  top: -80%;
}
.smallPlain{
  display: none;
}
.blue-title{
  display: flex;
  text-align: center;
  font-family: Poppins;
  font-style: normal;
  font-weight: 600;
  font-size: 36px;
  line-height: 124.5%;
  /* or 45px */

  text-align: center;

  color: #F2F5F9;
}
.blue-text{
  display: flex;
  text-align: center;
  font-family: Poppins;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 140%;
  /* or 25px */

  text-align: center;

  color: #CEE0EF;
  padding-top: 3rem;
  padding-bottom: 40px;
}
@media screen and (max-width: 769px){
.blockBlue{
  padding-top: 50px;
}
.blue-title{
  font-size: 24px;
}
.blue-text{
  font-size: 14px;
  padding-bottom: 0;
  padding-top: 25px;
}
.big{
  display: none;
  margin-top: 0;
}
.bigPlain{
  display: none;
}
.plainMobile{

}

.small{
  display: block;
  float: right;
}
.smallPlain{
  display: flex;
  position: absolute;
  left: 0;
  transform: translateY(95%);
}
}
@media screen and (max-width: 305px){
.smallPlain{
  transform: translateY(125%);
}
}
</style>
