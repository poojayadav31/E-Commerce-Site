<template>
    <footer class="footer">
      <div class="logo-container">
        <div v-for="(logo, index) in logos" :key="index" class="logo-item">
          <img :src="logo.src" :alt="logo.name" class="logo" />
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: "LogoList",
    data() {
      return {
        logos: [
          { name: "Logo 1", src: "img/logo-carousel/logo-1.png" },
          { name: "Logo 2", src: "img/logo-carousel/logo-2.png" },
          { name: "Logo 3", src: "img/logo-carousel/logo-3.png" },
          { name: "Logo 4", src: "img/logo-carousel/logo-4.png" },
          { name: "Logo 5", src: "img/logo-carousel/logo-5.png" },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
 
  .footer {
    background-color: #303030; 
    padding: 40px 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
  }
  
  
  .logo-container {
    display: flex;
    flex-wrap: wrap; 
    justify-content: center;
    gap: 80px; 
    width: 90%;
    max-width: 1200px; 
  }
  
  .logo-item {
    flex: 1 1 calc(25% - 20px); 
    max-width: 150px; 
    text-align: center;
  }
  
  .logo {
    max-width: 100%; 
    height: auto; 
    transition: transform 0.3s ease, opacity 0.3s ease;
  }
  
  .logo:hover {
    transform: scale(1.1);
    opacity: 0.8; 
  }
  
 
  @media (max-width: 768px) {
    .logo-item {
      flex: 1 1 calc(33.33% - 10px);
      max-width: 120px;
    }
    .logo-container {
      gap: 10px; 
    }
  }
  
 
  @media (max-width: 480px) {
    .logo-item {
      flex: 1 1 calc(50% - 10px); 
      max-width: 100px;
    }
  }
  </style>
  