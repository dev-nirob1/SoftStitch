<template>
  <!-- ======== Footer section ======== -->
  <footer class="footer">
    <div class="container medium-2 large-3 gap-2 py-1 medium-py-4">
      <!-- Footer logo and contact info -->
      <div class="contact-info">
        <a href="/" class="logo">
          <BaseImage image="/footer-logo.png" alt="Real Estate Logo" />
        </a>

        <BaseParagraph>
          Soft, warm, and made with care — our sweaters are crafted to bring comfort to every winter moment.
        </BaseParagraph>

      </div>

      <!-- Quick navigation links -->
      <div>
        <SubTitle>Contact Us</SubTitle>
        <ul class="footer-links">
          <ListItem>
            <i class="fa-solid fa-location-dot"></i> <span>SoftStitch HQ, Dhaka 1216, Bangladesh</span>
          </ListItem>
          <ListItem>
            <i class="fa-solid fa-phone"></i> +8801234567890
          </ListItem>
          <ListItem>
            <i class="fa-solid fa-envelope"></i> support@softStitch.com
          </ListItem>
        </ul>

      </div>


      <!-- Newsletter section -->
      <div class="social">
        <SubTitle>Follow Us On</SubTitle>
        <div class="social-links">
          <a href="https://www.facebook.com" target="_blank" rel="noopener noreferrer">
            <i class="fab fa-facebook-f"></i>
          </a>
          <a href="https://www.instagram.com" target="_blank" rel="noopener noreferrer">
            <i class="fab fa-instagram"></i>
          </a>
          <a href="https://wa.me/8801234567890" target="_blank" rel="noopener noreferrer">
            <i class="fab fa-whatsapp"></i>
          </a>
        </div>
        <BaseParagraph>Stay connected for new arrivals, style tips, and exclusive offers.</BaseParagraph>
      </div>
    </div>

    <!-- Footer bottom copyright -->
    <div class="footer-bottom">
      <BaseParagraph> &copy; {{ new Date().getFullYear() }} SoftStitch. Designed and developed by
        <a href="webpoka.com">Webpoka</a>
      </BaseParagraph>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: var(--dark-color);
  color: var(--white-color);
}

.footer .logo img {
  height: 70px;
  width: auto;
}

.footer .social-links {
  display: flex;
  gap: 1rem;
  font-size: 1.5rem;
}

.footer .social-links a {
  border-radius: .25rem;
  background: var(--white-color);
  color: var(--primary-color);
  padding: 0 .75rem;
}

.social-links a:hover {
  background: var(--primary-color);
  color: var(--white-color);
}

.footer .sub-title {
  margin-bottom: 1.5rem;
}

.footer ul li {
  margin: .75rem 0;
}

.footer-bottom {
  text-align: center;
  padding: .75rem;
  border-top: 1px solid rgb(from var(--border-color) r g b / 40%);
}

.footer-bottom p {
  font-size: 14px;
}

.footer-bottom a:hover {
  color: var(--primary-color);
}
</style>
