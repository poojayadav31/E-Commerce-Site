<template>
    <div class="gallery">
      <!-- Baris Foto -->
      <div class="photo-row">
        <div v-for="(photo, index) in photos" :key="index" class="photo-item">
          <!-- Overlay Header -->
          <div class="photo-header">
            <a 
              :href="`https://instagram.com/${photo.username}`" 
              target="_blank" 
              rel="noopener noreferrer" 
              class="instagram-link"
            >
              <img src="/img/instagram-white.png" alt="Instagram Icon" class="instagram-icon" />
              <span class="instagram-name">@{{ photo.username }}</span>
            </a>
          </div>
          <!-- Foto -->
          <img :src="photo.image" :alt="`Photo ${index + 1}`" class="photo" />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "Brandlist",
    data() {
      return {
        photos: [
          { image: "img/insta-1.jpg", username: "poojayadav_31" },
          { image: "img/insta-2.jpg", username: "poojayadav_31" },
          { image: "img/insta-3.jpg", username: "poojayadav_31" },
          { image: "img/insta-4.jpg", username: "poojayadav_31" },
          { image: "img/insta-5.jpg", username: "poojayadav_31" },
          { image: "img/insta-6.jpg", username: "poojayadav_31" },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
 
  .gallery {
    display: flex;
    flex-direction: column;
    margin-top: 20px;
    width: 100%; 
  }
  
 
  .photo-row {
    display: flex;
    flex-wrap: nowrap; 
    justify-content: space-between; 
    width: 100%;
  }
  
  .photo-item {
    flex: 1; 
    position: relative; 
    overflow: hidden; 
  }
  

  .photo-header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex; 
    justify-content: center; 
    align-items: center; 
    opacity: 0; 
    transition: opacity 0.3s ease; 
    background-color: rgba(0, 0, 0, 0.5); 
  }
  
  .photo-item:hover .photo-header {
    opacity: 1; 
  }
  
  .instagram-link {
    text-decoration: none; 
    color: inherit; 
    display: flex;
    flex-direction: column;
    align-items: center; 
  }
  
  .instagram-icon {
    width: 30px;
    height: 30px;
    margin-bottom: 8px; 
  }
  
  .instagram-name {
    font-size: 14px;
    color: #ffffff; 
    font-weight: bold;
  }
  
 
  .photo {
    width: 100%; 
    height: auto; 
    object-fit: cover;
    transition: transform 0.3s ease; 
  }
  
  
  @media (max-width: 768px) {
    .photo {
      height: 180px; 
    }
  }
  
  @media (max-width: 480px) {
    .photo {
      height: 100px; 
    }
  }
  </style>
  