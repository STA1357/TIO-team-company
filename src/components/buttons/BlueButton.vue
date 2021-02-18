<template>
  <div>
    <!-- Button trigger modal -->

    <button type="button" class="learn_btn" data-toggle="modal" data-target="#staticBackdrop">Learn more <span
      class="line"></span> >
    </button>

    <!-- Modal -->
    <div class="modal fade" id="staticBackdrop" data-backdrop="static" data-keyboard="false" tabindex="-1"
         style="height: auto" aria-labelledby="staticBackdropLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <div>
              <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            <div>
              <h5 class="modal-title pt-2" id="staticBackdropLabel">Any suggestions or questions? </h5>
            </div>
            <div class="modal-title-p">
              <p>We are waiting for your message with a question
                or suggestion to help you achieve your goal. </p>
            </div>
          </div>
          <div class="modal-body" style="margin: 0 5vw;">
            <div style="text-align: start">
              <label for="text" class="lab">Name</label>
            </div>
            <input type="text" id="text" class="custom-input pr-5" v-model="postBody" placeholder="Enter your name*"/>
            <div style="text-align: start">
              <label for="email" class="lab">Email</label>
            </div>
            <input type="email" id="email" class="custom-input pr-5" v-model="postEmail"
                   placeholder="Enter your email*"/>
            <div style="text-align: start">
              <label for="message" class="lab">Message</label>
              <textarea id="message"
                        rows="5"
                        class="form-control"
                        placeholder="Add your text"
                        v-model="message"
                        style="border: dashed 1px lightgrey;
                                height: 80px">
              </textarea>
            </div>
          </div>
          <div class="modal-footer">
            <div class="btn-send-hov">
              <button @click="postPost" type="button" data-dismiss="modal" class="btn-send">
                <span aria-hidden="true">Send request</span>
              </button>
            </div>
            <label for="agreement" class="agr-lab">
              <input type="checkbox"
                     id="agreement"
                     value="Agreement"
                     v-model="checkboxOptions">
              <span class="agr-span pl-2">I agree to receive occasional Team Technology
            Company newsletters containing news and advice on creating personal and business progress
            via digital tech.</span>
            </label>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'BlButton',
  data () {
    return {
      postBody: '',
      postEmail: '',
      checkboxOptions: [],
      message: ''
    }
  },
  props: {
    color: String
  },
  methods: {
    postPost: async function () {
      try {
        await axios.post('http://jsonplaceholder.typicode.com/posts', {
          body: this.postBody,
          email: this.postEmail,
          checkBox: this.checkboxOptions,
          msg: this.message
        })
      } catch (e) {
        this.errors.push(e)
      }
    }
  }
}
</script>

<style scoped lang="scss">
  .learn_btn {
    color: white;
    background: #0660FC;
    padding: 14px 22px;
    border: #0660FC;
    border-radius: 100px;
    font-style: normal;
    font-family: Poppins;
    font-weight: 600;
    font-size: 14px;
    line-height: 130%;

    /* identical to box height, or 21px */

    letter-spacing: 0.02em;
    outline: none;
    cursor: pointer;
  }

  .learn_btn:hover {
    color: black;
    background: none;
    border: 1px solid #0556E2;

    .line {
      margin-left: 10px;
      padding: 0 10px;
      border-left: 1px solid black;
      opacity: 0.7;
      height: 30px;
    }
  }

  .line {
    margin-left: 10px;
    padding: 0 10px;
    border-left: 1px solid lightgray;
    opacity: 0.7;
    height: 30px;
  }

  .modal-dialog {
    max-width: 845px;
  }

  .modal-content {
    background: #FFFFFF;
    border: 1px solid #CFD4D9;
    box-sizing: border-box;
    border-radius: 16px;
    padding: 30px 60px;
  }

  .modal-header {
    display: block;
    text-align: center;
    border-bottom: white;
  }

  .modal-footer {
    width: 100%;
    display: block;
    text-align: center;
    border-top: white;
  }

  .modal-title {
    display: inline-block;
    font-family: Poppins;
    font-style: normal;
    font-weight: 600;
    font-size: 32px;
    line-height: 124.5%;
    /* identical to box height, or 45px */

    /* Sub title_color */

    color: #333333;
  }

  .modal-title-p {
    margin-top: 24px;
    font-family: Poppins;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 140%;
    /* or 25px */

    text-align: center;

    /* Text_color */

    color: #333333;
    margin-left: 4vw;
    margin-right: 4vw;
  }

  .lab {
    margin-top: 24px;
    font-family: Poppins;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 130%;
    /* identical to box height, or 18px */

    letter-spacing: 0.01em;

    color: #000000;
  }

  .custom-input {
    color: #BECBE1;
    font-size: 14px;
    border-bottom: 1px solid #BECBE1;
    border-top: none;
    border-left: none;
    border-right: none;
    width: 100%;
  }

  .agr-span {
    font-family: SF Pro Display;
    font-style: normal;
    font-weight: 500;
    font-size: 11px;
    line-height: 134.85%;
    /* or 18px */

    letter-spacing: 0.01em;

    color: #BECBE1;
  }
  .btn-send-hov{
    margin: 0 5rem;
  }
  .btn-send {
    padding: 12px;
    border: 1px solid #0660FC;
    box-sizing: border-box;
    border-radius: 100px;
    width: 100%;
    color: black;
    cursor: pointer;
    background: none;
  }

  .btn-send:hover {
    color: #0660FC;
  }

  .agr-lab {
    margin-top: 15px;
    margin-left: 4vw;
    margin-right: 4vw;
  }
::placeholder{
  font-family: Poppins;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 177.81%;
  /* identical to box height, or 28px */

  letter-spacing: 0.01em;

  color: #BECBE1;
}
  @media screen and (max-width: 790px) {
    .modal-content {
      margin: 0 auto;
      height: auto;
      width: 90%;
      padding: 15px 20px;
    }
    .modal-header {
      padding: 0;
    }
    .modal-title {
      font-size: x-large;
      margin-bottom: 10px;
    }
    .modal-title-p {
      font-size: 12px;
      width: 302px;
      display: contents;
    }
    .agr-lab {
      display: none;
    }
    .btn-send-hov{
      margin: 0 1.5rem;
    }
  }
</style>
