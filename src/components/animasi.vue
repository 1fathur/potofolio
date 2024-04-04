<template>
  <div class="typing-text" :style="{ zIndex: zIndex }">
    {{ typedText }}
    <span v-if="showCursor" style="color: white;">|</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      texts: ["PORTOFOLIO CV","FATHUR"], 
      textIndex: 0,
      typedText: "",
      currentIndex: 0,
      typingSpeed: 100,
      eraseSpeed: 100,
      showCursor: true,
      zIndex: 3000
    };
  },
  mounted() {
    this.type();
  },
  methods: {
    type() {
      const interval = setInterval(() => {
        if (this.currentIndex < this.texts[this.textIndex].length) {
          this.typedText += this.texts[this.textIndex][this.currentIndex];
          this.currentIndex++;
        } else {
          clearInterval(interval);
          setTimeout(() => {
            this.erase();
          }, 1000);
        }
      }, this.typingSpeed);
    },
    erase() {
      const interval = setInterval(() => {
        if (this.currentIndex > 0) {
          this.typedText = this.typedText.slice(0, -1);
          this.currentIndex--;
        } else {
          clearInterval(interval);
          this.textIndex = (this.textIndex + 1) % this.texts.length; // Ganti ke teks baru setelah penghapusan selesai
          setTimeout(() => {
            this.type();
          }, 500);
        }
      }, this.eraseSpeed);
    }
  }
};
</script>

<style>
@import url('https://fonts.cdnfonts.com/css/sigmar');
.typing-text {
  color: gold;
  font-size: 50px;
  font-family: 'Sigmar', sans-serif;
  font-weight: bold;
  display: inline-block;
  position: relative;
  text-shadow: 0 0 5px burlywood,
               0 0 10px antiquewhite;
}
</style>
