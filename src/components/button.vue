<template>
    <div class="button-container">
      <button class="home-button" @mouseover="hoverEffect('home')" @mouseleave="resetHover('home')">Home</button>
      <button class="logout-button" @mouseover="hoverEffect('logout')" @mouseleave="resetHover('logout')">Logout</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      hoverEffect(button) {
        if (button === 'home') {
          document.querySelector('.home-button').classList.add('hovered');
        } else if (button === 'logout') {
          document.querySelector('.logout-button').classList.add('hovered');
        }
      },
      resetHover(button) {
        if (button === 'home') {
          document.querySelector('.home-button').classList.remove('hovered');
        } else if (button === 'logout') {
          document.querySelector('.logout-button').classList.remove('hovered');
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .button-container {
    display: flex;
    position: absolute;
    top: 20px;
    right: 20px;
    margin-right: -700px;
    margin-top: -370px;
  }
  
  .home-button,
  .logout-button {
    padding: 10px 20px;
    margin-right: 10px;
    border: none;
    border-top: 2px solid sandybrown;
    border-bottom: 2px solid sandybrown;
    background-color: transparent;
    color: #f1ee0d;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s ease;
    
  }
  
  .home-button:hover,
  .logout-button:hover {
    background-color: rgba(238, 252, 46, 0.5);
    border: none;
  }
  
  .hovered {
    background-color: #f0f0f0;
  }
  </style>
  