<template>
    <div class="button">
      <button @click="toggleButton">
        {{ buttonText }}
      </button>
      <transition name="slide">
        <div v-if="isVisible" class="slide">
          <p class="underline">About</p>
          <p>Teknologi Informasi (TI) adalah bidang yang berhubungan dengan <br>penggunaan komputer untuk mengumpulkan, menyimpan, mengamankan, <br>dan memanipulasi data. Ini melibatkan pengembangan perangkat lunak,<br> manajemen sistem komputer, analisis data, jaringan, keamanan siber.
</p>
          <p class="underline">Skills</p>
          <p>Sebagai seorang profesional di bidang Information Technology (IT), saya memiliki <br>keahlian dalam beberapa bahasa pemrograman dan teknologi terkait. Di antara <br>keahlian tersebut, saya menguasai HTML, CSS, Java, PHP, dan SQL.</p>
        </div>
      </transition>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isVisible: false
      };
    },
    methods: {
      toggleButton() {
        this.isVisible = !this.isVisible;
      }
    },
    computed: {
      buttonText() {
        return this.isVisible ? 'Hide Me' : 'Show Me';
      }
    }
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.cdnfonts.com/css/waiting-summer');
  @import url('https://fonts.cdnfonts.com/css/adlam-display');

  .slide-enter-active, .slide-leave-active {
    transition: all 0.5s;
  }
  .slide-enter, .slide-leave-to  {
    transform: translateY(100%);
    opacity: 0;
  }
  .underline {
    font-family: 'Waiting Summer', sans-serif;
    text-decoration: underline;
    font-weight: bold;
    font-size: 24px;
  }
  .button button{
    position: fixed;
    z-index: 5;
    left: 5%;
    top: 30%;
    font-size: 20px;
    background-color: transparent;
    border: 3px solid burlywood;
    color: blanchedalmond;
    text-shadow: 0 0 5px black,
                 0 0 10px lemonchiffon,
                 0 0 20px lavenderblush;
  }
  .slide {
    font-family: 'ADLaM Display', sans-serif;
    position: fixed;
    top: 40%;
    left: 5%;
    padding: 10px;
    color: chocolate;
    text-shadow: 0 0 3px black,
                 0 0 10px lemonchiffon;
  }
  </style>
  