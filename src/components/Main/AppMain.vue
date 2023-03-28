<script>
import CarouselComponent from './MainComponents/CarouselComponent.vue';
import HistoryComponent from './MainComponents/HistoryComponent.vue';
import CollectionsComponent from './MainComponents/CollectionsComponent.vue';
import WatchLabStudioComponent from './MainComponents/WatchLabStudioComponent.vue';
import DiscoverWatchLabComponent from './MainComponents/DiscoverWatchLabComponent.vue';
import GetInTouchComponent from './MainComponents/GetInTouchComponent.vue';

export default {
  name: "AppMain",

  components: {
    CarouselComponent,
    HistoryComponent,
    CollectionsComponent,
    WatchLabStudioComponent,
    DiscoverWatchLabComponent,
    GetInTouchComponent,
  }
}

</script>

<template>
  <CarouselComponent />
  <HistoryComponent />
  <CollectionsComponent />
  <WatchLabStudioComponent />
  <DiscoverWatchLabComponent />
  <GetInTouchComponent />
</template>

<style lang="scss">
@use "../../styles/general.scss" as *;

</style>