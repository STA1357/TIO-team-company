<template>
    <div class="container-fluid" style="position: absolute; background: #EBF1F9">
      <div class="footer-top">
        <div class="row">
          <span class="col-md-4 col-3 hid">
            <div class="pop">Contacts</div>
            <div class="pop pt-3">Location, street, address</div>
          </span>
          <span class="col-md-4 col-3 hid">
            <span class="pop">About</span>
            <span class="pop ml-5">Services</span>
            <span class="pop ml-5">Contact us</span>
          </span>
          <span class="col-md-4 col-12 poss">
            <div>
              <span class="pop">Subscribe to us in</span>
              <span class=" blue ml-3 desktopIcon">
                <i class="fab fa-facebook-f" style="padding: 0 3px"></i>
              </span>
              <span class="ml-3 white desktopIcon">
                <i class="fab fa-linkedin-in" style="padding: 0 1px"></i>
              </span>
              <div style="padding: 10px 0;">
                <span class=" blue mobileIcon">
                <i class="fab fa-facebook-f" style="padding: 0 3px"></i>
              </span>
              <span class="ml-3 white mobileIcon">
                <i class="fab fa-linkedin-in" style="padding: 0 1px"></i>
              </span>
              </div>
            </div>
            <div class="mt-2">
              <span>GoodFirm</span>
              <span class="ml-2">Clutch</span>
            </div>
          </span>
        </div>
      </div>
      <div class="footer-bottom">
        <div class="row" style="background: #01066E; padding: 20px 0">
          <span class="col-md-5 col-5 darkblue privacy">Privacy policy</span>
          <span class="col-md-7 col-7 darkblue">© Team technology COMPANY 2021</span>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped lang="scss">
.footer{
  padding-top: 50px;
}
.footer-bottom{
  color: white;
  background: #01066E;
  text-align: left;
}
.footer-top{
  text-align: left;
  padding: 50px 160px;
  background: #EBF1F9;
}
.hid{
  display: block;
}
.blue{
  color: white;
  border: 1px solid #0556E2;
  background-color: #0556E2;
  border-radius: 50%;
  padding: 3px;
}
.white{
  color: white;
  border: 1px solid #0556E2;
  background-color: #0556E2;
  border-radius: 50%;
  padding: 3px;
}
.pop{
  font-family: Poppins;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 143%;
  /* or 23px */

  letter-spacing: 0.02em;

  /* Text_color */

  color: #333333;
}
.darkblue{
  font-family: Poppins;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 130%;
  /* identical to box height, or 16px */

  letter-spacing: 0.02em;

  color: #EAF0F9;

}

.mobileIcon{
  display: none;
}
.poss{
text-align: end;
}
.privacy{
  padding-left: 175px;
}
@media screen and (max-width: 769px){
  .footer-top{
    text-align: center;
    padding: 10px 0;
  }
  .hid{
    display: none;
  }
  .darkblue{
    font-size: 9px;
  }
  .pop{
    font-size: 10px;
    font-weight: 600;
  }
  .desktopIcon{
    display: none;
  }
  .mobileIcon{
    display: initial;
  }
  .poss{
    text-align: center;
  }
  .privacy{
    padding-left: 20px;
  }
}
</style>
