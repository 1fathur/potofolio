<template>
  <div class="app">
    <bg />
    <div class="text">
      <animated-text />
    </div>
    <div class="lebah">
      <lebah />
    </div>
    <div class="icon">
      <icon-cv />
    </div>
    <div>
      <scroll-down />
    </div>
    <div class="button-container">
      <button-component />
    </div>
  </div>
</template>

<script>
import bg from './components/background.vue';
import AnimatedText from './components/animasi.vue'; 
import Lebah from './components/profile.vue';
import IconCv from './components/svgIcon.vue'; 
import ScrollDown from './components/scroll.vue';
import ButtonComponent from './components/button.vue'; // Import komponen button

export default {
  name: 'App',
  components: {
    bg,
    AnimatedText,
    Lebah,
    IconCv,
    ScrollDown,
    ButtonComponent // Daftarkan komponen button
  }
}
</script>

<style>
.icon {
  display: flex;
  position: fixed;
  width: 150px;
  z-index: 20;
  top: 200px;
  right: 350px;
  filter: drop-shadow(0 0 5px #000);
  margin: 0 50px;
}

.lebah {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-30%, -50%);
  z-index: -1;
}

.app {
  position: relative;
}

.text {
  z-index: 99;
  position: absolute;
  top: 50%;
  left: -500px;
  transform: translate(-50%, -400%);
}

.button-container {
  position: absolute;
  top: 20px;
  right: 20px;
}
</style>
