<template>
  <v-app dark>
  
    <v-app-bar :clipped-left="clipped" fixed app>
     
      
      <v-toolbar-title  >{{ $t(title) }}</v-toolbar-title>
      <v-spacer />
      <div v-for="data in items" :key="data" elevation="0" >
        <v-btn icon :to="localePath(data.to)">{{$t(data.title)}}</v-btn>
        
      </div>
      <v-spacer></v-spacer>
      <v-card elevation="0"
      v-if="$i18n.locale !== 'en'"
      :to="switchLocalePath('en')"
    >
      <img src="/en-flag.png" height="40" width="60"/>
    </v-card>

    <nuxt-link
      v-if="$i18n.locale !== 'la'"
      :to="switchLocalePath('la')"
    >
    <img src="/la-flag.png" height="40" width="60"/>

    </nuxt-link>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

  

    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      dialog: false,
      items: [
        {
          icon: "mdi-apps",
          title: 'HOME',
          to: "/"
        },
        {
          icon: "mdi-chart-bubble",
          title: "ABOUT",
          to: "/inspire"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "APBANK"
    };
  }
};
</script>

<style>
* {
  font-family: "Noto Sans Lao", sans-serif;
  font-optical-sizing: auto;
  font-weight: bold;
  font-style: normal;
  font-variation-settings: "wdth" 100;
}
.promote {
  z-index: 99999999999999999;
}
</style>
