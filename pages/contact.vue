<!-- Kian Naidoo - u25618670 -->
 <template>
  <div>
    <p class="section-label">Get In Touch</p>
    <h1>Contact Me</h1>
    <p class="contact-intro">Have a question or want to work together? Send me a message.</p>

    <form name="contact" method="POST" data-netlify="true" class="contact-form">
      <input type="hidden" name="form-name" value="contact" />
      <input type="text" name="name" placeholder="Your Name" required />
      <input type="email" name="email" placeholder="Email Address" required />
      <textarea name="message" placeholder="Your message..."></textarea>
      <button type="submit">Send Message</button>
    </form>
  </div>
</template>