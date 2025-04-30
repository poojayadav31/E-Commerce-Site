<template>
  <footer class="footer">
    <div class="footer-container">
      <!-- Logo Section -->
      <div class="footer-brand">
        <img src="../../public/img/blog/logo_website_ecom_white.png" alt="Ecom Logo" class="footer-logo" />
        <p>Address: Raipur, Chhattisgarh, India</p>
        <p>Phone: 9131617558</p>
        <p>Email: hello.Ecom@gmail.com</p>
        <div class="social-icons">
          <a href="https://www.facebook.com"><font-awesome-icon :icon="['fab', 'facebook']" class="icon" /></a>
          <a href="https://www.instagram.com/poojayadav_31/"><font-awesome-icon :icon="['fab', 'instagram']" class="icon" /></a>
          <a href="https://id.pinterest.com"><font-awesome-icon :icon="['fab', 'pinterest']" class="icon" /></a>
          <a href="https://wa.me/9131617558"><font-awesome-icon :icon="['fab', 'whatsapp']" class="icon" /></a>
          <a href="https://x.com"><font-awesome-icon :icon="['fab', 'twitter']" class="icon" /></a>
        </div>
      </div>
      
      <!-- Links Section -->
      <div class="footer-links">
        <div class="footer-information">
          <h4>Information</h4>
          <ul>
            <li><a href="#">About Us</a></li>
            <li><a href="#">Checkout</a></li>
            <li><a href="#">Contact</a></li>
            <li><a href="#">Services</a></li>
          </ul>
        </div>
        <div class="footer-account">
          <h4>My Account</h4>
          <ul>
            <li><a href="#">My Account</a></li>
            <li><a href="#">Contact</a></li>
            <li><a href="#">Shopping Cart</a></li>
            <li><a href="#">Shop</a></li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
.footer {
  background-color: #191919;
  color: #8b8b8b;
  padding: 50px 20px;
  font-family: Arial, sans-serif;
}

.footer-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}


.footer-brand {
  max-width: 300px;
  margin-bottom: 20px;
}

.footer-logo {
  width: 120px;
  margin-bottom: 10px;
}


.footer-links {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 100%;
}

.footer-links h4 {
  color: #ffffff;
  font-size: 16px;
  margin-bottom: 10px;
}

.footer-links ul {
  list-style: none;
  padding: 0;
}

.footer-links ul li {
  margin-bottom: 5px;
}

.footer-links ul li a {
  color: #8b8b8b;
  text-decoration: none;
}

.footer-links ul li a:hover {
  text-decoration: underline;
}

.social-icons {
  display: flex;
  gap: 10px;
  justify-content: center;
  margin-top: 10px;
}

.social-icons a {
  color: #fff;
  font-size: 18px;
  text-decoration: none;
}


@media (min-width: 768px) {
  .footer-container {
    flex-direction: row;
    justify-content: space-between;
    text-align: left;
    align-items: flex-start;
    max-width: 1200px;
    margin: 0 auto;
  }

  .footer-brand {
    max-width: 400px;
    text-align: left;
  }

  .footer-links {
    flex-direction: row;
    justify-content: space-between;
    width: 50%;
  }

  .social-icons {
    justify-content: flex-start;
  }
}
</style>