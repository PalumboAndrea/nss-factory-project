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
            <div class="col-12 col-lg-6">
                <p class="mainTitle mb-0">
                    Press from
                    <br>
                    Watch Lab Studio
                </p>
            </div>
        </div>
        <div class="row g-0">
            <div class="col-12 col-md-4">
                <p class="mt-3 mt-lg-5 text w-100 text-start pe-md-4">
                    On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain trouble
                </p>
            </div>
            <div class="col-12 col-md-5 image pb-4 mt-5 mt-md-0">
                <transition name="fade" mode="out-in">
                    <img :src="getImagePath(images[actualIndex].name)" alt="image" class="img-fluid" :key="actualIndex">
                </transition>
            </div>
            <div class="col-12 col-md-3 ps-0 ps-md-2 ps-lg-5 text-start textContainer">
                <span class="text-uppercase fw-bold">
                    press
                </span>
                <transition name="slide-fade" mode="out-in">
                    <p class="text-uppercase mb-4 mb-md-5 date" :key="actualIndex">
                        {{images[actualIndex].date}}
                    </p>
                </transition>
                <transition name="slide-fade" mode="out-in">
                    <p class="textTitle pe-3 mb-0" :key="actualIndex">
                        {{images[actualIndex].title}}
                    </p>
                </transition>
                <div class="iconContainer mt-5 text-center text-md-start">
                    <font-awesome-icon :icon="['fas', 'chevron-left']" role="button" class="me-5" @click="carouselIndexBack"/>
                    <font-awesome-icon :icon="['fas', 'chevron-right']" role="button" @click="carouselIndexForward" />
                </div>
                <div class="greyBackground d-flex d-sm-none d-md-flex position-absolute"></div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;

.slide-fade-enter-from{
  opacity: 0;
  transform: translateX(-5px);
}

.slide-fade-enter-to{
  opacity: 1;
  transform: translateX(0);
}

.slide-fade-enter-active
{
  transition: all 0.3s;
}

.fade-enter-from{
  opacity: 0.5;
}

.fade-enter-to{
  opacity: 1;
}

.fade-enter-active
{
  transition: all 0.3s;
}

@include media-breakpoint-down(md) {
    .main-container{
        margin-bottom: 30px;
        .greyBackground{
            width: 100%;
            left: 0;
            top: 410px;
        }
    }
}

    .textTitle{
        min-height: 135px;
    }
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