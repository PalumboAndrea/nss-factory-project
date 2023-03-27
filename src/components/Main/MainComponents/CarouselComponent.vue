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
        <div class="carouselText d-flex flex-column m-auto text-center align-items-center">
            <img :src="getImagePath(content[actualIndex].img)" alt="" id="mainImg">
            <p class="text-uppercase mb-5 uppercaseTitle">
                london collection season
            </p>
            <p class="mainTitle mb-1">
                {{ content[actualIndex].upperTitle }}
                <br>
                {{ content[actualIndex].lowerTitle }}
            </p>
            <p class="subtitle mt-2">
                An estimable experience in the modern collection house
            </p>
            <div>
                <button class="mt-5">
                    Discover
                </button>
            </div>
        </div>

        <div class="position-absolute previewNextSlide" @click="carouselIndex">
            <img :src="getImagePath(content[otherIndex].img)" alt="" id="previewImg">
            <div class="previewNextSlideContent">
                <p class="previewNextSlideTitle m-5">
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
    </div>
    
</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;

.carouselContainer{
    height: calc(100vh - $headerHeight);
    color: white;

    .mainTitle{
        line-height: 90px;
    }

    #mainImg{
        padding: 0;
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;
        z-index: -1;
        object-fit: cover;
    }

    .previewNextSlide{
        right: 70px;
        bottom: 0;
        height: 300px;
        width: 440px;
        transition: 0.3s;
        cursor: pointer;
        overflow: hidden;
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
            font-size: 26px;
            transition: 0.3s;
            font-family: $titleFont;
        }
        &:hover .previewNextSlideTitle{
            font-size: 33px;
        }
        &:hover #previewImg{
            transform: scale(1.2);
        }
        &:hover .iconNone{
            opacity: 1;
        }
        #previewImg{
            padding: 0;
            position: absolute;
            top: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            object-fit: cover;
            transition: 0.3s all ease-in-out;
        }
    }

    .mainTitle{
        font-size: 4rem;
    }

    button{
        @include carouselButton;
    }
}

</style>