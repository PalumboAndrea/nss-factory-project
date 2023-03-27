<script>
import HeaderComponent from './components/HeaderComponent.vue';
import AppMain from './components/Main/AppMain.vue';

export default {
  name: "App",

  components: {
    HeaderComponent,
    AppMain,
  }
}

</script>

<template>
  <HeaderComponent />
  <AppMain />

</template>

<style lang="scss">
@use "./styles/general.scss" as *;

</style>
