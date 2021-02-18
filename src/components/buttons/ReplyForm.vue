<template>
  <form
    id="app"
    @submit="checkForm"
    action="https://vuejs.org/"
    method="post"
    novalidate="true"
    style="background: white; padding: 0 15px;"
  >
    <div class="replyForm">
      <div class="row">
        <div class="col-md-6 col-12 contact-col">
          <label for="text">Name</label>
          <input type="text" id="text" class="custom-input pl-2" v-model="postBody" placeholder="Enter your name*"/>
          <p v-if="errors.length">
            <b>Name is required</b>
          </p>
        </div>
        <div class="col-md-6 col-12 contact-col">
          <label for="email">Email</label>
          <input type="email" id="email" class="custom-input pl-2" v-model="postEmail" placeholder="Enter your email*"/>
          <p v-if="errors.length">
            <b>Email is required</b>
          </p>
        </div>
      </div>
      <div class="row">
        <div class="col-md-6 col-12 contact-col">
          <label for="industry">Industry</label>
          <input type="industry" id="industry" class="custom-input pl-2" v-model="postIndustry" placeholder="Enter your industry*"/>
        </div>
        <div class="col-md-6 col-12 contact-col">
          <label for="budget">Budget</label>
          <div class="select">
            <select name="budget"
                    id="budget"
                    class="custom-input pl-2"
                    v-model="postBudget"
            style="width: 100%; font-family: Poppins;
            font-style: normal;
            font-weight: 500;
            font-size: 14px;
            line-height: 130%;
            letter-spacing: 0.01em;
            color: #BECBE1;">
              <option value="default" disabled>
                Select your annual budget</option>
              <option value="5000">5000</option>
              <option value="10000">10000</option>
              <option value="15000">15000</option>
            </select>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12 col-12">

          <div class="goal">Your goal</div>
          <div class="checkGroup">
            <label for="teambox">
              <input type="checkbox"
                     class="check"
                     id="teambox"
                     value="Teambox"
                     v-model="checkboxOptions">
              <span style="padding-left: 8px; padding-right: 8px">Team expansion</span>
            </label>

            <label for="custom">
              <input type="checkbox"
                     class="check"
                     id="custom"
                     value="Custom"
                     v-model="checkboxOptions"> <span style="padding-left: 8px; padding-right: 8px">Custom project</span>
            </label>
            <label for="maintenance">
              <input type="checkbox"
                     class="check"
                     id="maintenance"
                     value="Maintenance"
                     v-model="checkboxOptions"> <span style="padding-left: 8px">Maintenance team</span>
            </label>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12 col-12 contact-col">
          <label for="message" class="messager">Message</label>
          <textarea id="message"
                    placeholder="Let us know a bit more details about your business"
                    rows="5"
                    class="form-control"
                    style="color: gray; border-style: dashed; margin-bottom: 10px"
                    v-model="message"></textarea>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12 col-12 superInput">
          <label for="file"
          style="border: 1px solid lightgray;border-style: dashed; width: 100%; text-align: center; padding: 20px 0;"
          >Attach file</label>
          <input type="file"
                 id="file"
                 ref="file"
                 style="border: none; outline: none;display: none;"
                 @change="previewFiles" multiple
                 @click='pickFile'>
        </div>
      </div>
      <div class="row" style="margin: 10px 0.5vw;">
        <div class="col-md-12 col-12 send-btn-div">
          <button @click="checkBeforeSend" class="send-btn">Send request</button>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12 col-12 agr-div">
          <label for="agreement" style="display: flex; margin: 0 5vw;">
            <input type="checkbox"
                   class="agreement"
                   id="agreement"
                   value="Agreement"
                   v-model="checkboxOptions">
            <span class="agr-span pl-1">I agree to receive occasional Team Technology
            Company newsletters containing news and advice on creating personal and business progress
            via digital tech.</span>
          </label>
        </div>
      </div>
    </div>

  </form>
</template>

<script>
import axios from 'axios'
export default {
  name: 'ReplyForm',
  data () {
    return {
      errors: [],
      postBody: null,
      postEmail: null,
      postIndustry: null,
      postBudget: 'default',
      checkboxOptions: [],
      fileBox: '',
      message: ''
    }
  },
  methods: {
    checkBeforeSend () {
      if (this.errors.length) {
        return this.postPost()
      }
    },
    postPost: async function () {
      try {
        await axios.post('http://jsonplaceholder.typicode.com/posts', {
          body: this.postBody,
          email: this.postEmail,
          industry: this.postIndustry,
          budget: this.postBudget,
          checkBox: this.checkboxOptions,
          msg: this.message,
          files: this.fileBox
        })
      } catch (e) {
        this.errors.push(e)
      }
    },
    previewFiles () {
      this.files = this.$refs.myFiles.files
    },
    pickFile () {
      this.files = this.$refs.myFiles.click()
    },
    checkForm: function (e) {
      this.errors = []

      if (!this.postBody) {
        this.errors.push('Name required.')
      }
      if (!this.postEmail) {
        this.errors.push('Email required.')
      } else if (!this.validEmail(this.postEmail)) {
        this.errors.push('Valid email required.')
      }

      if (!this.errors.length) {
        return true
      }

      e.preventDefault()
    },
    validEmail: function (postEmail) {
      const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
      return re.test(postEmail)
    }
  }
}
</script>

<style scoped lang="scss">
  *,
  *::before,
  *::after {
    box-sizing: border-box;
  }

  .superInput{
    display: flex;
    justify-content: center;
  }

.contact-col{
display: grid;
  padding-top: 30px;
}

label{
  text-align: start;
  font-family: Poppins;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 130%;
  /* identical to box height, or 18px */

  letter-spacing: 0.01em;

  color: #000000;

}
::-webkit-input-placeholder {
  font-family: Poppins;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 130%;
  /* or 21px */

  letter-spacing: 0.01em;

  color: #BECBE1;
}
.custom-input{
  border-top: none;
  border-left: none;
  border-right: none;
  border-bottom: 1px solid lightgray;
  outline: none;
  background: none;
}
.goal{
  font-family: Poppins;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 177.81%;
  /* or 28px */

  letter-spacing: 0.01em;

  color: #000000;
  text-align: start;
  padding-top: 2rem;
}
.checkGroup{
  text-align: start;
  padding-top: 2rem;
  display: flex;
}

.send-btn-div{
  border: 1px solid #0660FC;
  border-radius: 100px;
  margin-top: 40px;
}
.send-btn{
  background: none;
  border: none;
  padding: 16px 0;
}

.agr-div{
  padding-top: 30px;
  padding-bottom: 50px;
}
.agr-span{
  font-family: SF Pro Display;
  font-style: normal;
  font-weight: 500;
  font-size: 13px;
  line-height: 19px;
  letter-spacing: 0.01em;

  color: #BECBE1;
}

  .select {
    position: relative;
    display: inline-block;
  }
  .select:after {
    content: url("../../assets/arrowdown.svg");
    padding: 0 8px;
    font-size: 12px;
    position: absolute;
    right: 0;
    top: 0;
    z-index: 1;
    text-align: center;
    width: 10%;
    height: 100%;
    pointer-events: none;
    box-sizing: border-box;
  }
  select {
    padding-right: 25px;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
  }
@media screen and (max-width: 769px) {
  .checkGroup {
    display: grid;
  }
  .send-btn-div {
    margin-top: 0;
  }
}
</style>
