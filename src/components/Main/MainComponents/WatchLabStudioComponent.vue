<script>

export default {
    name: "WatchLabStudioComponent",
    components: {

    },
    data(){
        return{
            actualIndex: 0,
            images: [
                {
                    date: '18 settembre 2022',
                    title: 'Most Important Days on Watchlab',
                    name: 'important_days.png',
                },
                {
                    date: '23 settembre 2022',
                    title: 'Winner Of Best Manifacture',
                    name: 'best_manifacture.png',
                }
            ]
        }
    },
    methods: {
    carouselIndexBack(){
        if (this.actualIndex == 0){
            this.actualIndex = (this.images.length - 1);
        } else {
            this.actualIndex--
        }
    },
    carouselIndexForward(){
        if (this.actualIndex == (this.images.length - 1)){
            this.actualIndex = 0
        } else {
            this.actualIndex++
        }
    },
    getImagePath: function (imgPath){
        return new URL(`/src/assets/imgs/${imgPath}`, import.meta.url).href;
    }
  }
}

</script>

<template>
    <div class="container-fluid main-container position-relative">
        <div class="row g-0">
            <div class="col-6">
                <p class="mainTitle mb-0">
                    Press from
                    <br>
                    Watch Lab Studio
                </p>
            </div>
        </div>
        <div class="row g-0">
            <div class="col-4">
                <p class="mt-5 text w-75">
                    On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain trouble
                </p>
            </div>
            <div class="col-5 image pb-4">
                <img :src="getImagePath(images[actualIndex].name)" alt="image" class="img-fluid">
            </div>
            <div class="col-3 ps-5">
                <span class="text-uppercase fw-bold">
                    press
                </span>
                <p class="text-uppercase mb-5 date">
                    {{images[actualIndex].date}}
                </p>
                <p class="textTitle fs-3 pe-3">
                    {{images[actualIndex].title}}
                </p>
                <div class="iconContainer mt-5">
                    <font-awesome-icon :icon="['fas', 'chevron-left']" role="button" class="me-5" @click="carouselIndexBack"/>
                    <font-awesome-icon :icon="['fas', 'chevron-right']" role="button" @click="carouselIndexForward" />
                </div>
                <div class="greyBackground position-absolute"></div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;
    .date{
        color: $mainColor;
    }
    .greyBackground{
        background-color: rgb(217,217,217);
        height: 100%;
        width: 45%;
        right: 70px;
        top: 0;
        z-index: -1;
    }
</style>