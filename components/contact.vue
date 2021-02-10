<template>
  <form
    name="contact"
    action="/"
    method="post"
    netlify
    data-netlify-honeypot="bot-field"
  >
    <input type="hidden" name="form-name" value="contact"/>
    <p>
      <label>Your Name: <input type="text" name="name" required/></label>
    </p>
    <p>
      <label for="subject">Subject:</label>

      <select name="subject" id="subject" required>
        <option value="general inquiry">General Inquiry</option>
        <option value="order a paddle">Order a Paddle</option>
      </select>
    </p>
    <p>
      <label>Your Email: <input type="email" name="email" required/></label>
    </p>
    <p>
      <label>Message: <textarea name="message" required></textarea></label>
    </p>
    <p>
      <button type="submit" value="Send message">Send</button>
    </p>
  </form>
</template>

