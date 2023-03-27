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
}

</script>

<template>
    <div class="container main-container text-center my-5">
        <div class="row" :class="((index % 2 !== 0) ? 'flex-row-reverse' : '')" v-for="(text, index) in texts">
            <div class="col-6 d-flex flex-column justify-content-center align-items-center textContainer">
                <p class="text-uppercase fw-bold">
                    {{ text.collection }}
                </p>
                <p class="fs-1">
                    {{ text.title }}
                </p>
                <p class="textGray">
                    {{ text.description }}
                </p>
                <div>
                    <button class="mt-5">
                        View
                    </button>
                </div>
            </div>
            <div class="col-6 image-container"></div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;


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
        background-color: blue;
        height: 500px;
    }
</style>