<template>
<div>
  <div class="topnav" id="myTopnav" ref="myTopnav">
    <div class="first-nav">
      <router-link to="/">
        <img src="./assets/tio.svg" alt="tio" class="tioLogo">
        <span class="team"><span class="bl">TEAM </span>Technology
      <br>Company</span>
      </router-link>
    </div>
    <div class="special-float">
      <router-link to="/"></router-link>
      <router-link to="/about" style="margin-top: 0.8rem;">Services</router-link>
      <router-link to="/test" style="margin-top: 0.8rem;">About</router-link>
      <router-link to="/contact" class="routDesktop" style="box-shadow: 0 2px 5px lightgray;">Contact</router-link>
    </div>
    <a href="javascript:void(0);" class="icon" @click="myFunction">
      <i class="fa fa-bars" style="margin-top: 2px;
    border: 1px solid rgb(6, 96, 252);
    padding: 8px;
    border-radius: 50%;"></i>
    </a>
  </div>
  <router-view/>
</div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.routDesktop{
  border: 1px solid #0660FC;
  border-radius: 100px;
  padding: 4px 42px!important;
  margin-top: 0.5rem;
  margin-left: 30px;
}
.bl{
  color: #0660FC;
  font-weight: 600;
}
.topnav {
  overflow: hidden;
  background-color: white;
  position: fixed;
  width: 100%;
  z-index: 10;
  padding: 10px 0;
  border-top: 3px solid #0F37B0;
}

.topnav a {
  float: left;
  display: flex;
  color: black;
  text-align: center;
  padding: 2px 10px;
  text-decoration: none;
  font-size: 14px;
  font-family: Poppins;
}

.topnav a:hover {
  color: grey;
}

.topnav a.active {
  background-color: #4CAF50;
  color: white;
}

.topnav .icon {
  display: none;
}
.tioLogo{
  height: 38px;
}
.team{
  display: block;
  text-align: start;
  line-height: 120%;
  font-family: Poppins;
  font-style: normal;
  line-height: 140%;
  /* or 17px */

  letter-spacing: 0.03em;
  text-transform: uppercase;
}
.first-nav{
  margin-left: 5rem;
}
.special-float{
  display: inline-block;
  margin-left: 40rem;
}
@media screen and (min-width: 1678px){
  .special-float{
    margin-left: 55rem;
  }
}
@media screen and (max-width: 1283px){
  .special-float{
    margin-left: 25rem;
  }
  .first-nav{
    margin-left: 0;
  }
}
@media screen and (max-width: 769px) {
  .topnav a:not(:first-child) {display: none;}
  .topnav a.icon {
    float: right;
    display: block;
  }
  .special-float{
    margin-left: 0;
  }
  .first-nav{
    margin-left: 0;
    text-decoration: none;
  }
}

@media screen and (max-width: 769px) {
  .topnav.responsive {position: fixed;}
  .topnav.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
    padding-top: 12px;
  }
  .topnav.responsive a {
    float: none;
    display: block;
    text-align: center;
  }
  .tioLogo{
    display: none;
  }
  .team{
    display: block;
    text-align: start;
  }
  .routDesktop{
    border: 1px solid #0660FC;
    border-radius: 100px;
    padding: 6px 42px!important;
    margin: 0.5rem 30vw;
    box-shadow: 0 2px 5px lightgrey;
  }
}
</style>
<script>
export default {
  name: 'App',
  methods: {
    myFunction () {
      const x = this.$refs.myTopnav
      if (x.className === 'topnav') {
        x.className += ' responsive'
      } else {
        x.className = 'topnav'
      }
    }
  }
}
</script>
