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
            <div class="col-6 position-relative text-center">
                <img :src="getImagePath('Rectangle_9.png')" alt="" class="img-fluid">
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
            <div class="col-6">
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