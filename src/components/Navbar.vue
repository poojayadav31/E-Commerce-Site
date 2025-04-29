<template>
  <nav class="navbar">
    <div class="container">
      <!-- Logo -->
      <div class="logo">
        <a href="/">
          <img src="/img/logo_website_Ecom.png" alt="MyLogo" />
        </a>
      </div>

     <!-- Hamburger Menu (Only on Mobile) -->
     <div class="hamburger" @click="toggleMenu">
      <img v-if="!isMenuActive" src="/img/more.png" alt="Hamburger Menu" />
      <img v-else src="/img/close.png" alt="Close Menu" />
     </div>

      <!-- Navigation Links (Desktop) -->
      <div class="nav-links" v-show="!isMenuActive || windowWidth > 768">
        <router-link to="/" class="nav-link" :class="{ active: isActive('/') }">Home</router-link>
        <router-link to="/product" class="nav-link" :class="{ active: isActive('/product') }">Detail</router-link>
        <router-link to="/checkout" class="nav-link" :class="{ active: isActive('/checkout') }">Checkout</router-link>
        <router-link to="/final" class="nav-link" :class="{ active: isActive('/final') }">Success</router-link>
      </div>
    </div>
  </nav>

  <!-- Sidebar Menu (Mobile) -->
  <div class="sidebar" :class="{ 'active': isMenuActive }">
    <div class="close-icon" @click="closeMenu">
      <img src="/img/close.png" alt="Close Menu" />
    </div>
    <router-link to="/" class="nav-link" :class="{ active: isActive('/') }" @click.native="closeMenu">Home</router-link>
    <router-link to="/product" class="nav-link" :class="{ active: isActive('/product') }" @click.native="closeMenu">Detail</router-link>
    <router-link to="/checkout" class="nav-link" :class="{ active: isActive('/checkout') }" @click.native="closeMenu">Checkout</router-link>
    <router-link to="/final" class="nav-link" :class="{ active: isActive('/final') }" @click.native="closeMenu">Success</router-link>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      isMenuActive: false,
      windowWidth: window.innerWidth
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuActive = !this.isMenuActive;
    },
    closeMenu() {
      this.isMenuActive = false;
    },
    isActive(route) {
      return this.$route.path === route;
    },
    updateWidth() {
      this.windowWidth = window.innerWidth;
    }
  },
  mounted() {
    window.addEventListener("resize", this.updateWidth);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.updateWidth);
  }
};
</script>

<style scoped>

.navbar {
  background-color: #ffffff;
  width: 100%;
  padding: 25px 0;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 30px;
  margin-bottom: 30px;
  position: relative;
  z-index: 1000;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 0 30px;
}

.logo img {
  width: 160px;
  height: auto;
  display: block;
}


.hamburger {
  display: none;
  cursor: pointer;
  position: relative;
  z-index: 1100;
}

.hamburger img {
  width: 30px;
  height: auto;
}


.sidebar {
  position: fixed;
  top: 0;
  right: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(255, 255, 255, 0.95);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transform: translateX(100%);
  transition: transform 0.3s ease;
  z-index: 1200;
}

.sidebar.active {
  transform: translateX(0);
}


.close-icon {
  position: absolute;
  top: 50px; 
  right: 25px;
  cursor: pointer;
  border-radius: 50%; 
  padding: 10px; 
  transition: background-color 0.3s ease;
}

.close-icon img {
  width: 25px; 
  height: auto;
}

.nav-link {
  color: #000;
  text-decoration: none;
  font-size: 18px;
  padding: 15px 0;
  transition: color 0.3s ease;
}

.nav-link.active {
  color: #e7ab3b;
  font-weight: bold;
}


.nav-links {
  display: flex;
  gap: 20px;
}

@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  .hamburger {
    display: block;
  }
}
</style>
