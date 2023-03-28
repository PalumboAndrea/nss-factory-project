<script>
import HeaderComponent from './components/HeaderComponent.vue';
import AppMain from './components/Main/AppMain.vue';
import FooterComponent from './components/Footer/FooterComponent.vue';

export default {
  name: "App",

  components: {
    HeaderComponent,
    AppMain,
    FooterComponent,
  }
}

</script>

<template>
  <HeaderComponent />
  <AppMain />
  <FooterComponent />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;

</style>
