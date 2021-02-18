<template>
    <div class="blockContact">
      <div class="row contact">
        <div class="col-md-3 col-12 desktop-left">
          <img :src="`${options.image}`">
        </div>
        <div class="col-md-6 col-12">
          <span class="title mb-3">{{options.title}}</span>
          <div style="padding: 10px 0">
            <ReplyForm></ReplyForm>
          </div>
        </div>
        <div class="col-md-3 col-12 desktop-right">
          <img :src="`${options.imageTwo}`" class="dogDesktop">
          <img :src="`${options.imageTwoMobile}`" class="dogMobile">
        </div>
      </div>
    </div>
</template>

<script>
import ReplyForm from './buttons/ReplyForm'
export default {
  name: 'BlockContact',
  components: { ReplyForm },
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
  .blockContact{
    background: white;
    padding-top: 50px;
    margin-top: -6%;
  }
  .contact{
    margin: 0 2vw;
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
  }
  .desktop-left{
    display: flex;
    align-items: flex-end;
    padding: 0 5vw;
  }
  .desktop-right{
    display: flex;
    align-items: flex-end;
    padding: 0 5vw;
  }
  .dogMobile{
    display: none;
  }
  @media screen and (max-width: 769px){
    .blockContact{
      padding-top: 0;
      background: rgba(6, 96, 252, -0.97);
      padding-bottom: 0;
    }
    .desktop-left{
      display: none;
    }
    .desktop-right{
      padding: 0;
      display: block;
    }
    .dogDesktop{
      display: none;
    }
    .dogMobile{
      display: block;
      float:right;
      z-index: 10;
      margin-top: -45px;
      margin-right: 1rem;
    }
    .title{
      font-size: 22px;
    }
  }
</style>
