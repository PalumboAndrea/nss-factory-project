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
        <div class="container-fluid p-4 p-sm-5">
            <div class="row g-0">
                <div class="col-12 ms-4 ms-sm-0 mb-0 mb-sm-5 p-0 d-flex d-xs-block justify-content-start position-relative">
                    <img :src="getImagePath('logo.png')" alt="logo" id="logo" class="mx-auto mx-sm-0">
                </div>
            </div>
            <hr class="d-block d-sm-none">
            <div class="row d-flex">
                <div class="col-sm-4 order-3 mb-3 mb-sm-0 order-sm-1 text-center text-sm-start">
                    <hr class="d-block d-sm-none mt-1">
                    <ul>
                        <li v-for="element in footerMenu[0]" class="mb-0 mb-sm-3 address">
                            {{ element }}
                        </li>
                    </ul>
                </div>
                <div class="col-6 col-sm-3 order-1 order-sm-2">
                    <ul>
                        <li v-for="element in footerMenu[1]" class="mb-3">
                            {{ element }}
                        </li>
                    </ul>
                </div>
                
                <div class="col-6 col-sm-3 order-2 order-sm-3 text-end text-sm-start">
                    <ul>
                        <li v-for="element in footerMenu[2]" class="mb-3">
                            {{ element }}
                        </li>
                    </ul>
                </div>
                <div class="col-sm-2 order-4 order-sm-4 text-center text-sm-start">
                    <ul>
                        <li v-for="element in footerMenu[3]" class="mb-3">
                            {{ element }}
                        </li>
                    </ul>
                </div> 
            </div>
        </div>
        <hr class="m-0">
        <div class="container-fluid p-5 d-none d-sm-block">
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
    background-color: $footerBackground;
    color: $mainColor;
    font-family: $titleFont;
    p{
        margin: 0;
    }
    #logo{
        transform: scale(0.8);
        transform-origin: center left;
    }
    li{
        font-size: 13px;
    }
}

@include media-breakpoint-down(sm) {
    #logo{
        transform: scale(1);
    }
    #wrapper{
        li{
            font-size: 17px;
            
        }
        .address{
            font-family: $titleFont;
        }
    }
}
</style>