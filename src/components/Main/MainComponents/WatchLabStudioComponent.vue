<script>

export default {
    name: "WatchLabStudioComponent",
    components: {

    },
    data(){
        return{
        }
    },
}

</script>

<template>
    <div class="container mainContainer my-5">
        <div class="row">
            <div class="col-4">
                <h2 class="fs-1">
                    Press from Watch Lab Studio
                </h2>
                
            </div>
        </div>
        <div class="row">
            <div class="col-4">
                <p class="textGray mt-4">
                    On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain trouble
                </p>
            </div>
            <div class="col-5 image">

            </div>
            <div class="col-3 ps-5">
                <span class="text-uppercase fw-bold">
                    press
                </span>
                <p class="text-uppercase mb-5">
                    18 settembre 2015
                </p>
                <h4>
                    Most Important Days on Watchlab
                </h4>
                <div class="iconContainer mt-5">
                    <font-awesome-icon :icon="['fas', 'chevron-left']" class="me-5"/>
                    <font-awesome-icon :icon="['fas', 'chevron-right']" />
                </div>
            </div>
        </div>

    </div>

</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;

    .image{
        background-color: blue;
        height: 400px;
    }


</style>