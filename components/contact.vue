<template>
  <v-card>
  <form
    name="contact"
    action="/"
    method="post"
    netlify
    data-netlify-honeypot="bot-field"
  >
    <input type="hidden" name="form-name" value="contact"/>
    <ul class="form-style-1">
      <li>
        <label>Your Name <span class="required">*</span>
          <input type="text" name="name" class="field-long" placeholder="Name" required/>
        </label>
      </li>
      <li>
        <label>Email <span class="required">*</span>
          <input type="email" name="email" class="field-long" placeholder="Email" required/>
        </label>
      </li>
      <li>
        <label>Subject <span class="required">*</span>
          <select name="subject" class="field-select" required>
            <option value="General Inquiry">General Inquiry</option>
            <option value="Order a Paddle">Order a Paddle</option>
          </select></label>
      </li>
      <li>
        <label>Message <span class="required">*</span>
          <textarea name="message" id="message" class="field-long field-textarea" required></textarea>
        </label>
      </li>
      <v-col
        cols="12"
        class="flex-center"
      >
      <li>
        <button type="submit" value="Send message">Send</button>
      </li>
      </v-col>

    </ul>
  </form>
  </v-card>
</template>

<style type="text/css">
  .form-style-1 {
    margin:10px auto;
    max-width: 400px;
    padding: 20px 12px 10px 20px;
    font: 13px "Lucida Sans Unicode", "Lucida Grande", sans-serif;
  }
  .form-style-1 li {
    padding: 0;
    display: block;
    list-style: none;
    margin: 10px 0 0 0;
  }
  .form-style-1 label{
    margin:0 0 3px 0;
    padding:0px;
    display:block;
    font-weight: bold;
  }
  .form-style-1 input[type=text],
  .form-style-1 input[type=date],
  .form-style-1 input[type=datetime],
  .form-style-1 input[type=number],
  .form-style-1 input[type=search],
  .form-style-1 input[type=time],
  .form-style-1 input[type=url],
  .form-style-1 input[type=email],
  textarea,
  select{
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    border:1px solid #BEBEBE;
    padding: 7px;
    margin:0px;
    -webkit-transition: all 0.30s ease-in-out;
    -moz-transition: all 0.30s ease-in-out;
    -ms-transition: all 0.30s ease-in-out;
    -o-transition: all 0.30s ease-in-out;
    outline: none;
  }
  .form-style-1 input[type=text]:focus,
  .form-style-1 input[type=date]:focus,
  .form-style-1 input[type=datetime]:focus,
  .form-style-1 input[type=number]:focus,
  .form-style-1 input[type=search]:focus,
  .form-style-1 input[type=time]:focus,
  .form-style-1 input[type=url]:focus,
  .form-style-1 input[type=email]:focus,
  .form-style-1 textarea:focus,
  .form-style-1 select:focus{
    -moz-box-shadow: 0 0 8px #88D5E9;
    -webkit-box-shadow: 0 0 8px #88D5E9;
    box-shadow: 0 0 8px #88D5E9;
    border: 1px solid #88D5E9;
  }
  .form-style-1 input[type=submit],
  .form-style-1 button{
    border: none;
    padding: 8px 60px 8px 60px;
    background: #FF8500;
    color: #fff;
    border-radius: 3px;
    -webkit-border-radius: 3px;
    -moz-border-radius: 3px;
  }
  .form-style-1 input[type=submit]:hover,
  .form-style-1 button:hover{
    background: #EA7B00;
    color: #fff;
  }
  .form-style-1 .field-divided{
    width: 49%;
  }

  .form-style-1 .field-long{
    background-color: white;
    width: 100%;
  }
  .form-style-1 .field-select{
    background-color: white;
    width: 100%;
  }
  .form-style-1 .field-textarea{
    background-color: white;
    height: 100px;
  }
  .form-style-1 input[type=submit], .form-style-1 input[type=button]{
    background: #4B99AD;
    padding: 8px 15px 8px 15px;
    border: none;
    color: #fff;
  }
  .form-style-1 input[type=submit]:hover, .form-style-1 input[type=button]:hover{
    background: #4691A4;
    box-shadow:none;
    -moz-box-shadow:none;
    -webkit-box-shadow:none;
  }
  .form-style-1 .required{
    color:red;
  }
</style>
