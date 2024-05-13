<template>
 <div :class="{sticky: sticky}">
  
   <v-card>
    <v-tabs
    v-model="tab"
    background-color="primary"
    dark
    flat
      grow
      show-arrows
    >
      <v-tab @click="toggleMenu(1)" :value="1">About</v-tab>
      <v-tab @click="toggleMenu(2)" :value="2">Currency</v-tab>
      <v-tab @click="toggleMenu(3)" :value="3">Tab 2</v-tab>
      <v-tab @click="toggleMenu(4)" :value="4">Tab 2</v-tab>
      <v-tab @click="toggleMenu(5)" :value="5">Tab 2</v-tab>
    </v-tabs>
   </v-card>
   

<div v-if="showMenuTab1">
  <p>This is the content for Tab 1.</p>
</div>
<v-card v-if="showMenuTab2" class='primary white--text'>
 <v-card-text>
  <li v-for="(data, idx) in 10" :key="idx" class="white--text">
    huevang {{idx + 1}}
  </li>
 </v-card-text>
</v-card>
 </div>
</template>

<script>
export default {
  data() {
    return {
      tab: null,
      showMenuTab1: false,
      showMenuTab2: false
    };
  },
  methods: {
    toggleMenu(tabNumber) {
      if (tabNumber === 1) {
        this.showMenuTab1 = !this.showMenuTab1;
        this.showMenuTab2 = false; // Hide menu for tab 2
      } else if (tabNumber === 2) {
        this.showMenuTab2 = !this.showMenuTab2;
        this.showMenuTab1 = false; // Hide menu for tab 1
      }
    }
  }
};
</script>

<style scoped>
.header{
  position: relative;
  z-index:99999
}
  .sticky{
    position:fixed;
    top:7.5%;
    width: 98%;
    margin-left: -22px;
    box-shadow: 0 0 10px rgba(0,0,0, 0.1);
  }
</style>
