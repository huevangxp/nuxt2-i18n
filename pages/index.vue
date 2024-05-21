<template>
  <div class = 'd-flex justify-center' style="margin-top: 200px">

    <h1   class="card text">{{currentTime}}</h1>

  </div>
</template>

<script>
export default {
  data() {
    return {
      currentTime: null,
    };
  },
  mounted() {
    this.startClock();
  },
  methods: {
    startClock() {
      setInterval(() => {
        this.currentTime = new Date().toLocaleTimeString();
      }, 1000);
    },
  },
};
</script>

<style>
.card{
  transition: transform 6s ease-in-out;
  color: teal;
}
.card:hover{
  transform: scale(1.10);
}
.text {
  background-image: url('https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_640.jpg');
  background-size: cover;
  background-clip:text;
  -webkit-background-clip:text;
  color:transparent;
  font-size:250px;

}
</style>
