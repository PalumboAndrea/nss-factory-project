<script>
export default {
  name: "CarouselComponent",
  data(){
        return{
            actualIndex: 0,
            otherIndex: 1,
            text: [
                {
                    upperTitle: 'New Selection of',
                    lowerTitle: 'Henry London',
                    img: 'slider-bike-4.jpg',
                },
                {
                    upperTitle: 'The Path to Success',
                    lowerTitle: 'with Watchlab',
                    img: 'slider-bike-9.jpg',
                }
            ]
        }
    },
  components: {

  },
  methods: {
    carouselIndex(){
        if (this.actualIndex == (this.text.length - 1)){
            this.actualIndex = 0
            this.otherIndex = 1
        } else {
            this.actualIndex++
            this.otherIndex--
        }
    },
  }
}

</script>

<template>
    <div class="container-fluid p-0 carouselContainer d-flex align-items-center position-relative">
        <div class="carouselText d-flex flex-column w-50 m-auto text-center align-items-center">
            <p class="text-uppercase mb-5">
                london collection season
            </p>
            <p class="mainTitle m-0">
                {{ text[actualIndex].upperTitle }}
                <br>
                {{ text[actualIndex].lowerTitle }}
            </p>
            <span>
                An estimable experience in the modern collection house
            </span>
            <button class="w-25 mt-4">
                Discover
            </button>
        </div>
        

        <div class="position-absolute previewNextSlide" @click="carouselIndex">
            <div class="previewNextSlideContent">
                <p class="previewNextSlideTitle m-5">
                    {{ text[otherIndex].upperTitle }}
                    <br>
                    {{ text[otherIndex].lowerTitle }}
                </p>
                <span class="text-uppercase position-absolute">
                    next >
                </span>
            </div>
            
        </div>
    </div>
    
</template>

<style lang="scss">
@use "../../../styles/general.scss" as *;

.carouselContainer{
    height: calc(100vh - $headerHeight);
    background-color: red;
    color: white;

    .previewNextSlide{
        right: 70px;
        bottom: 0;
        background-color: blue;
        height: 300px;
        width: 450px;
        transition: 0.3s;
        cursor: pointer;
        span{
            bottom: 10px;
            right: 20px;
        }
        .previewNextSlideTitle{
            font-size: 1.2rem;
            transition: 0.3s;
        }
        &:hover .previewNextSlideTitle{
            font-size: 2rem;
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