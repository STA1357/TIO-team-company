<template>
  <div class="home" style="background: rgba(6, 96, 252, 0.03);">
    <Block
      :options="{
    title: 'Find a software \n'+
            ' development team \n'+
              ' for your project',
    text: 'We match your business with IT vendors ' +
            ' in Ukraine which best suit your budget ' +
               'and project requirements.',
    image: require('../assets/firstPic.svg'),
    imageMobile: require('../assets/firstPicMobile.svg'),
    imagePlain: require('../assets/firstPlain.svg'),
    imagePlainMobile: require('../assets/firstPlainMobile.svg')
  }"
    ></Block>
    <BlockTwo
      :options="{
    title: 'Work with carefully-selected software companies',
    image: require('../assets/twomans.svg'),
    imageMobile: require('../assets/twomansMobile.svg')
  }"
    ></BlockTwo>
    <BlockThree
      :options="{
    title: 'Let us handle vendor analysis and interviewing ',
    imageText: require('../assets/good.svg'),
    image: require('../assets/think.svg'),
    imageMobile: require('../assets/thinkMobile.svg')
  }"
    ></BlockThree>
    <BlockFour
      :options="{
    title: 'Get detailed report on team’s'+
            ' tech '+
            ' stack, capabilities '+
            ' & experience',
    text:'We carefully select and analyze the software development companies according to your ' +
          ' business requirements and budget and will provide a detailed report on their capabilities ' +
          ' and estimates for your project. ' ,
    image: require('../assets/typerDesktop.svg'),
    imageMobile: require('../assets/typerMobile.svg')
  }"
    ></BlockFour>
    <BlockBlue
    :options="{
      title: 'Delegate full-cycle project \n'+
              ' management to us',
      text: 'We can help you manage the project from start to ﬁnish while you focus on your business operations and marketing. This will help you save time and energy on meetings\n'+
              'and communication.',
      image: require ('../assets/blueBlockPlain.svg'),
      imageMobile: require('../assets/blueBlockPlainMobile.svg'),
      imageTwo: require ('../assets/blueBlockFlower.svg'),
      imageTwoMobile: require ('../assets/blueBlockFlowerMobile.svg')
    }"
    ></BlockBlue>
    <BlockStatistic
    :options="{
      title: 'How we work',
      image: require('../assets/statisticDesktop.svg'),
      imageMobile: require('../assets/statisticMobile.svg')
    }"
    ></BlockStatistic>
    <BlockContact
    :options="{
      title: 'Reach out to us',
      image:require('../assets/contactFlowerDesktop.svg'),
      imageTwo:require('../assets/contactDogDesktop.svg'),
      imageTwoMobile: require('../assets/contactDogMobile.svg')
    }"
    ></BlockContact>
    <Footer></Footer>
  </div>
</template>

<script>
import Block from '../components/Block'
import BlockTwo from '../components/BlockTwo'
import BlockThree from '../components/BlockThree'
import BlockFour from '../components/BlockFour'
import BlockBlue from '../components/BlockBlue'
import BlockStatistic from '../components/BlockStatistic'
import BlockContact from '../components/BlockContact'
import Footer from '../components/Footer'

export default {
  name: 'Home',
  components: {
    Footer,

    BlockContact,
    BlockStatistic,
    BlockBlue,
    BlockFour,
    Block,
    BlockTwo,
    BlockThree
  }
}
</script>
<style lang="scss">
  .home{
  }
  @media screen and (max-width: 282px){
    .home{
      overflow: auto;
    }
  }
</style>
