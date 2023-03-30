<script>

export default {
    name: "DiscoverWatchLabComponent",
    components: {

    },
    data(){
        return{
            
        }
    },
    methods: {
        getImagePath(imgPath){
            return new URL(`/src/assets/imgs/${imgPath}`, import.meta.url).href;
        }
    }
}

</script>

<template>
    <div class="container-fluid main-container position-relative">
        <div class="row g-0">
            <div class="col-12 col-md-6 position-relative text-center imgContainer">
                <img :src="getImagePath('Rectangle_9.png')" alt="" class="img-sm-fluid">
                <div class="d-flex flex-column justify-content-center align-items-center position-absolute top-50 start-50 translate-middle w-100">
                    <p class="text-uppercase uppercaseTitle">
                        instagram
                    </p>
                    <p class="mainTitle text-nowrap">
                        Discover
                        <br>
                        Watch Lab
                    </p>
                </div>
            </div>
            <div class="col-12 col-md-6">
                <div class="row g-0">
                    <div class="col-6">
                        <img :src="getImagePath('Rectangle 10.png')" alt="" class="img-fluid h-100 w-100">
                    </div>
                    <div class="col-6">
                        <img :src="getImagePath('Rectangle 11.png')" alt="" class="img-fluid h-100 w-100">
                    </div>
                </div>
                <div class="row g-0">
                    <div class="col-6">
                        <img :src="getImagePath('Rectangle 12.png')" alt="" class="img-fluid h-100 w-100">
                    </div>
                    <div class="col-6">
                        <img :src="getImagePath('Rectangle 13.png')" alt="" class="img-fluid h-100 w-100">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;


    @include media-breakpoint-down(md) {
        .main-container{
            padding: 0;
            margin: 0;
            .imgContainer{
                height: 800px;
                overflow: hidden;
                display: flex;
                justify-content: center;
                img{
                    object-fit: cover;
                    overflow: hidden;
                }
            }
            .mainTitle{
                font-size: 50px;
                line-height: 70px;
            }
            .uppercaseTitle{
                margin-bottom: 0;
                line-height: 20px;
            }
        } 
    }

    .imgContainer{
        height: 100%;
        overflow: hidden;
        display: flex;
        justify-content: center;
        img{
            object-fit: cover;
            overflow: hidden;
        }
    }

    .uppercaseTitle{
        letter-spacing: 3px;
        font-size: 13px;
    }
    .mainTitle{
        line-height: 100px;
        transform: scale(0.8);
    }

    p{
        color: white;
    }
    
</style>