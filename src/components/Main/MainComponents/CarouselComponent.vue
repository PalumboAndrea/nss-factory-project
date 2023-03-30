<script>
export default {
  name: "CarouselComponent",
  data(){
        return{
            actualIndex: 0,
            otherIndex: 1,
            content: [
                {
                    upperTitle: 'New Selection of',
                    lowerTitle: 'Henry London',
                    img: 'table.png',
                },
                {
                    upperTitle: 'The Path to Success',
                    lowerTitle: 'with Watchlab',
                    img: 'watch.png',
                }
            ]
        }
    },
  components: {

  },
  methods: {
    carouselIndex(){
        if (this.actualIndex == (this.content.length - 1)){
            this.actualIndex = 0
            this.otherIndex = 1
        } else {
            this.actualIndex++
            this.otherIndex--
        }
    },
    getImagePath: function (imgPath){
        return new URL(`/src/assets/imgs/${imgPath}`, import.meta.url).href;
    }
  }
}

</script>

<template>
    <div class="container-fluid p-0 carouselContainer d-flex align-items-center position-relative">
        <div class="carouselText d-flex flex-column m-auto text-center align-items-center pt-5">
            <transition name="fade" mode="out-in">
                <img :src="getImagePath(content[actualIndex].img)" alt="" id="mainImg" class="img-fluid" :key="content[actualIndex].img">
            </transition>
            <p class="text-uppercase mb-5 uppercaseTitle">
                london collection season
            </p>
            <transition name="slide-fade" mode="out-in">
                <p class="mainTitle mt-3 mb-3" :key="content[actualIndex].upperTitle">
                    {{ content[actualIndex].upperTitle }}
                    <br>
                    {{ content[actualIndex].lowerTitle }}
                </p>
            </transition>
            <p class="subtitle">
                An estimable experience in the modern collection house
            </p>
            <div>
                <button class="mt-5">
                    Discover
                </button>
            </div>
        </div>

        <div class="previewNextSlide" @click="carouselIndex">
            <img :src="getImagePath(content[otherIndex].img)" alt="" class="img-fluid previewImg">
            <div class="previewNextSlideContent">
                <p class="previewNextSlideTitle">
                    {{ content[otherIndex].upperTitle }}
                    <br>
                    {{ content[otherIndex].lowerTitle }}
                </p>
                <div class="text-uppercase position-absolute next m-0">
                    <span>next</span>
                    <div class="iconContainer d-flex justify-content-center align-items-center position-absolute">
                        <font-awesome-icon :icon="['fas', 'chevron-right']" class="icon"/>
                        <font-awesome-icon :icon="['fas', 'chevron-right']" class="icon iconNone"/>
                        <font-awesome-icon :icon="['fas', 'chevron-right']" class="icon iconNone"/>
                    </div>
                </div>
            </div>
        </div>
        <!-- this is needed for down lg breakpoint -->
        <div class="text-uppercase position-absolute nextSM m-0" @click="carouselIndex">
            <span>next</span>
            <div class="iconContainer d-flex justify-content-center align-items-center position-absolute">
                <font-awesome-icon :icon="['fas', 'chevron-right']" class="icon"/>
                <font-awesome-icon :icon="['fas', 'chevron-right']" class="icon iconNone"/>
                <font-awesome-icon :icon="['fas', 'chevron-right']" class="icon iconNone"/>
            </div>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;

.slide-fade-enter-active {
  transition: all 0.2s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.2s ease-in;
}

.slide-fade-enter-from{
  transform: translateX(-10px);
  opacity: 0;
}
.slide-fade-leave-to {
  transform: translateX(10px);
  opacity: 0;
}


.fade-enter-active,
.fade-leave-active {
  transition: all 0.1s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0.9;
}



.carouselContainer{
    height: calc(100vh - $headerHeight);
    color: white;

    #mainImg{
        padding: 0;
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;
        z-index: -1;
        object-fit: cover;
    }

    .nextSM{
        display: none;
        font-family: $uppercaseTitleFont;
        font-weight: 700;
        letter-spacing: 3px;
        cursor: pointer;
        &:hover .iconNone{
            opacity: 1;
        }
        @include media-breakpoint-down(lg) {
            display: flex;
            bottom: 10px;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    }
    .iconContainer{
        left: 75px;
        bottom: 0;
        transform: translate(0, -50%);
        .icon{
            font-size: 0.8rem;
            margin-right: 2px;
        }
        .iconNone{
            opacity: 0;
            transition: opacity 0.3s ease-out;
        }
    }

    .previewNextSlide{
        position: absolute;
        right: 70px;
        bottom: 0;
        height: 300px;
        width: 440px;
        transform: scale(0.8);
        transform-origin: bottom center;
        transition: 0.3s;
        cursor: pointer;
        overflow: hidden;
        @include media-breakpoint-down(xxl) {
            transform: scale(0.7);
            transform-origin: bottom right;
        }
        @include media-breakpoint-down(xl) {
            transform: scale(0.6);
            transform-origin: bottom right;
        }
        @include media-breakpoint-down(lg) {
            display: none;
        }
        .next{
            font-family: $uppercaseTitleFont;
            font-weight: 700;
            bottom: 40px;
            right: 80px;
            letter-spacing: 3px;
        }
        .iconContainer{
            left: 75px;
            bottom: 0;
            transform: translate(0, -50%);
            .icon{
                font-size: 0.8rem;
                margin-right: 2px;
            }
            .iconNone{
                opacity: 0;
                transition: opacity 0.3s ease-out;
            }
        }
        .previewNextSlideTitle{
            font-size: 22px;
            transition: 0.3s;
            margin: 40px;
            font-family: $titleFont;
        }
        .previewImg{
            filter: brightness(0.8);
            padding: 0;
            position: absolute;
            top: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            object-fit: cover;
            transition: 0.3s all ease-in-out;
        }
        &:hover .previewImg{
            transform: scale(1.2);
        }
        &:hover .previewNextSlideTitle{
            font-size: 30px;
        }
        &:hover .iconNone{
            opacity: 1;
        }
    }

    button{
        @include carouselButton;
    }
}

</style>