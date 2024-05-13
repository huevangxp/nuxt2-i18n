<template>
  <div>
    <h1>{{ $t('HOME') }}</h1>

   
  </div>
</template>

<script>
export default {
  data: () => ({
    model: null,
    slideGroup: 0 
  }),
  mounted() {
    this.interval = setInterval(() => {
      // Increment slideGroup by 1
      this.slideGroup++;
      
      // If slideGroup reaches the last slide, reset it to 0
      if (this.slideGroup >= 25) {
        this.slideGroup = 0;
      }
    }, 5000);
  },
  created() {
    clearInterval(this.interval); // Clear the interval to prevent memory leaks
  }
}
</script>

<style>
.image{
  position: absolute;
  top: -40px; /* Adjust as needed */
  left: 50%; /* Adjust as needed */
  transform: translateX(-50%);
}
</style>
