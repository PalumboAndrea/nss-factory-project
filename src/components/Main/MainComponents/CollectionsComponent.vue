<script>

export default {
    name: "CollectionsComponent",
    components: {

    },
    data(){
        return{
            texts: [
                {
                    collection: 'london collection season',
                    title: 'Temporary Store',
                    description: 'On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire',
                    img: '',
                },
                {
                    collection: 'london collection season',
                    title: 'New Collection Henry London',
                    description: 'On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire',
                    img: '',
                }
            ]
        }
    },
    methods: {
    getImagePath: function (imgPath){
        return new URL(`/src/assets/imgs/${imgPath}`, import.meta.url).href;
    }
  }
}

</script>

<template>
    <div class="container-fluid main-container text-center">
        <div class="row g-0" :class="((index % 2 !== 0) ? 'flex-row-reverse' : '')" v-for="(text, index) in texts">
            <div class="col-12 d-flex d-sm-none image-container p-0">
                <img :src="((index % 2 !== 0) ? getImagePath('houseHenryLondon.png') : getImagePath('houseTemporaryStore.png'))" alt="image">
            </div>
            <div class="col-12 col-xl-6 d-flex flex-column justify-content-center align-items-center textContainer">
                <div class="w-100 w-lg-75">
                    <p class="text-uppercase fw-bold mb-3 mb-sm-2">
                    {{ text.collection }}
                    </p>
                    <p class="mainTitle mb-3 mb-sm-5">
                        {{ text.title }}
                    </p>
                    <p class="text">
                        {{ text.description }}
                    </p>
                    <div>
                        <button class="mt-3 mt-sm-5">
                            View
                        </button>
                    </div>
                </div>
            </div>
            <div class="d-none d-sm-flex col-xl-6 image-container p-0">
                <img :src="((index % 2 !== 0) ? getImagePath('houseHenryLondon.png') : getImagePath('houseTemporaryStore.png'))" alt="image" class="mx-auto">
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../../../styles/general.scss' as *;

@include media-breakpoint-down(sm) {
    .main-container{
        padding: 0;

        .textContainer{
            padding: 30px 20px
        }
    }
}

.textContainer{
    padding: 60px;
    button{
        @include carouselButton;
        &:hover{
            border: 1px solid $mainColor;
        }
    }
}
.image-container{
    
    overflow: hidden;
    img{
        max-width: 100%;
        object-fit: cover;
        transition: 0.3s all ease-in-out;
    }

    &:hover img{
        transform: scale(1.2);
    }
}
</style>