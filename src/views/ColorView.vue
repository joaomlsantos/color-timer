<script>
export default {
  data() {
    return {
      colors: ['#ff0000', '#00ff00', '#0000ff', '#ffffff', '#ffff00'], 
      currentColorIndex: 0,
      intervalId: null
    };
  },
  created() {
    this.changeColor();
    this.intervalId = setInterval(this.changeColor, 5000);
  },
  destroyed() {
    clearInterval(this.intervalId);
  },
  methods: {
    changeColor() {
        var randomIndex = this.currentColorIndex;
        while (randomIndex === this.currentColorIndex) {
          randomIndex = Math.floor(Math.random() * this.colors.length);
        }
        this.currentColorIndex = randomIndex;
        console.log(this.currentColorIndex);
        document.body.style.backgroundColor = this.colors[randomIndex];
    }
  }
};
</script>

<template>
</template>

<style>
</style>
