<script>
export default {
  name: "FooterComponent",

  data(){
    return{
        footerMenu: [
            [
                'Watch/Lab - Innovation brings success',
                'Via Borgona 5, Milan',
                'Italy',
            ],
            [
                'Abous us',
                'brand',
                'Projects',
                'Magazine',
            ],
            [
                'Press',
                'Contacts',
                'Privacy Policy',
                'Search',
            ],
            [
                'T. +39 392 9133937',
                'M. info@watch-lab.it',
                'FACEBOOK',
                'INSTAGRAM',
            ]
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
    <div id="wrapper">
        <div class="container-fluid p-5">
            <div class="row g-0">
                <div class="col-12 mb-5 p-0 d-flex justify-content-start position-relative">
                    <img :src="getImagePath('logo.png')" alt="logo" id="logo">
                </div>
            </div>
            <div class="row">
                <div class="col-4">
                    <ul>
                        <li v-for="element in footerMenu[0]" class="mb-3">
                            {{ element }}
                        </li>
                    </ul>
                </div>
                <div class="col-3">
                    <ul>
                        <li v-for="element in footerMenu[1]" class="mb-3">
                            {{ element }}
                        </li>
                    </ul>
                </div>
                <div class="col-3">
                    <ul>
                        <li v-for="element in footerMenu[2]" class="mb-3">
                            {{ element }}
                        </li>
                    </ul>
                </div>
                <div class="col-2">
                    <ul class="">
                        <li v-for="element in footerMenu[3]" class="mb-3">
                            {{ element }}
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <hr class="m-0">
        <div class="container-fluid p-5">
            <div class="row">
                <div class="col-10">
                    <p>
                        Copyright Watch/Lab all rights reserved
                    </p>
                </div>
                <div class="col-2">
                    <p>
                        Website by nssfactory
                    </p>
                </div>
            </div>
        </div>
    </div>
    

</template>

<style lang="scss" scoped>
@use "../../styles/general.scss" as *;

#wrapper{
    p{
        margin: 0;
    }
    background-color: $footerBackground;
    color: $mainColor;
    font-family: $titleFont;
    #logo{
        transform: scale(0.8);
        transform-origin: center left;
    }
    li{
        font-size: 13px;
    }
}
</style>