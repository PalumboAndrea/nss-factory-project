<script>
import CarouselComponent from './MainComponents/CarouselComponent.vue';
import HistoryComponent from './MainComponents/HistoryComponent.vue';
import CollectionsComponent from './MainComponents/CollectionsComponent.vue';
import WatchLabStudioComponent from './MainComponents/WatchLabStudioComponent.vue';


export default {
  name: "AppMain",

  components: {
    CarouselComponent,
    HistoryComponent,
    CollectionsComponent,
    WatchLabStudioComponent,
  }
}

</script>

<template>
  <CarouselComponent />
  <HistoryComponent />
  <CollectionsComponent />
  <WatchLabStudioComponent />
  
</template>

<style lang="scss">
@use "../../styles/general.scss" as *;

</style>