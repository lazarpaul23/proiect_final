<template>
  <Layout>
    <div class="contact flex flex-wrap flex-row-reverse">
      <div class="col-xl-1"></div>
      <div class="col-xl-5 text-center">
        <img class="contact-image" src="../../static/contact.png" alt="Contact">
      </div>
      <div class="col-xl-5">
        <h1>Let's connect!</h1>
        <p class="pt-12 pb-4">Do you have a project? Don't hesitate to contact me! </p>
        <div>
          <form  
            v-on:submit.prevent="onSubmit()"
            method="POST">
            <div class="input-area">                       
              <input type="text" v-model="name" required>
              <span class="floating-label">First and Last name</span>
            </div>
            <div class="input-area">
              <input type="text" v-model="email" required>
              <span class="floating-label">E-mail Address</span>
            </div>
            <div class="input-area">
              <textarea rows="5" v-model="message" required></textarea>
              <span class="floating-label">Tell me your idea!</span>
            </div>
            <div class="submit" >
                <input class="submit mx-auto" type="submit" value="Send">
            </div>
          </form> 
        </div>
      </div>
    </div>
    <div>
      <iframe width="100%" height="400" src="https://maps.google.com/maps?hl=en&amp;q=Nicolae Colan 10+()&amp;ie=UTF8&amp;t=&amp;z=10&amp;iwloc=B&amp;output=embed" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"></iframe>
    </div>
  </Layout>
</template>

<script>
import axios from "axios";

export default {
  metaInfo: {
    title: 'Contact'
  },
  data() {
    return {
      message: "",
      name: "",
      email: ""
    }
  },
  methods: {
    onSubmit() {
      let data = {
        name: this.name,
        email: this.email,
        message: this.message,
      };
      axios
        .post("https://getform.io/f/90ec02c1-d463-4dd9-8a6c-3fc679d1da5a/", data, {
          headers: {
            Accept: "application/json"
          }
        })
        .then( response => {
            this.name = "";
            this.email = "";
            this.message = "";
          } 
        );
    }
  }
}
</script>

<style scoped>
  .nvs {
    position: relative;
    text-align: right;
    height: 325px;
    width: 643px;
  } 

  #gmap_canvas img {
    max-width: none!important;
    background: none!important
  }

  input {
    height: 3.125rem; 
  }

  input:not([type="submit"]), textarea {
    border: 0;
    border-bottom: 1px solid #666;
    border-radius: 0;
    background: transparent;
    display: -moz-inline-stack;
    display: inline-block;
    vertical-align: bottom;
    *vertical-align: auto;
    zoom: 1;
    *display: inline;
    margin: 0 0 1rem 0;
    padding: 10px 0;
    width: 100%;
  }

  input:focus, textarea:focus {
    outline: none;
  }

  input:focus ~ .floating-label,
  input:not(:focus):valid ~ .floating-label,
  textarea:focus ~ .floating-label,
  textarea:not(:focus):valid ~ .floating-label{
    top: 0px;
    bottom: 10px;
    left: 0px;
    font-size: 12px;
    opacity: 1;
  }

  input[type="submit"] {
    background: #f16228;
    border: 1px solid #f16228;
    max-width: 200px;
    font-weight: 600;
    padding: 10px 30px;
    border-radius: 25px;
    margin-bottom: 20px;  
    color: white;
  }

  input[type="submit"]:hover {
    background: white;
    color: #f16228;
  }


  input[type="submit"]:focus, input[type="submit"]:active {
    outline: none;
  }

  .contact-address {
    max-width: 350px;
  }

  .contact-image {
    max-width: 100%;
  }

  .contact-location {
    background: #FDE9F3;
    padding: 100px 5%
  }

  .em {
    height: 1em;
  }

  .floating-label {
    position: absolute;
    pointer-events: none;
    left: 0px;
    top: 25px;
    transition: 0.2s ease all;
  }

  .input-area {
    margin: 5x 0;
    padding: 20px 0;
    position: relative
  }

@media (min-width: 1024px) {
  .contact {
    display: flex;
    padding-bottom: 5%;
    max-width: 680px;
    margin: auto;
  }
  .contact-image {
    padding: 5% 0 0 10%
  }

  .contact-image:before {
    width: 90%;
    height: 80%;
    right: -10%;
    bottom:  -20%;
  }

  .contact-location {
    padding: 100px 10%
  }
}

@media (min-width: 1280px) {

  .contact-location {
    padding: 100px 15%
  }

  .contact {
    max-width: 1280px;
  }
}

@media (max-width: 767px) {
  .contact-image {
    max-width: 300px;
    margin-bottom: 40px;
  }
}

</style>