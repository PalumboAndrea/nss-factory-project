<script>
export default {
    name: "HeaderComponent",
    data() {
        return {
            headerMenuTitles: ['Abous Us', 'Brand', 'Projects', 'Magazine', 'Press', 'Contacts'],
            displayNone: 'd-none',
        }
    },
    methods: {
    getImagePath: function (imgPath){
        return new URL(`/src/assets/imgs/${imgPath}`, import.meta.url).href;
    },
    removeNoneToHiddenMenu(){
        if(this.displayNone == ''){
            this.displayNone = 'd-none';
        } else {
            this.displayNone = '';
        }
    }
  }
}
</script>

<template>
    <div id="header-container" class="container-fluid p-0 sticky-top">
        <div class="row h-100 g-0">
            <div class="col-3 d-flex align-items-center headerTitle">
                <img :src="getImagePath('logo.png')" alt="logo" id="logo" class="ps-3">
            </div>
            <div class="col col-xl-7">
                <div class="row h-100 g-0 d-flex justify-content-evenly position-relative">
                    <div class="col-2 menuItem" v-for="headerMenuTitle in headerMenuTitles">
                        <span class="headerTitles">
                            {{ headerMenuTitle }}
                        </span>
                    </div>
                    <!-- this hidden menu is shown when the viewport is under 1200px -->
                    <div class="hiddenMenu position-relative">
                        <transition name="fade" mode="out-in">
                            <font-awesome-icon :icon="['fas', 'bars']" class="menuIcon" @click="removeNoneToHiddenMenu" v-if="displayNone"/>
                            <font-awesome-icon :icon="['fas', 'x']" class="menuIcon" @click="removeNoneToHiddenMenu" v-else/>
                        </transition>
                        <transition name="fade" mode="out-in">
                            <div id="hiddenMenuItem" class="text-center" :class="displayNone" :key="displayNone">
                                <div class="hiddenSearchBar py-2">
                                    <input type="text" class="searchInput me-1 p-0 m-0">
                                    <font-awesome-icon :icon="['fas', 'magnifying-glass']" class="searchIcon"/>
                                </div>
                                <p class="hiddenHeaderTitles m-0" v-for="headerMenuTitle in headerMenuTitles">
                                    <span role="button" >{{ headerMenuTitle }}</span>
                                </p>
                            </div>
                        </transition>
                    </div>
                </div>
            </div>
            <div class="col p-0 pe-3 searchBar">
                <input type="text" class="searchInput me-1 p-0 m-0">
                <font-awesome-icon :icon="['fas', 'magnifying-glass']"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss" as *;

.fade-enter-active,
.fade-leave-active {
  transition: all 0.1s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0.5;
}

#header-container{
    height: $headerHeight;
    background-color: white;
    @include media-breakpoint-down(xl) {
        background-color: $mainColor;
    }
    .headerTitle{
        background-color: $mainColor;
        height: 100%;
        width: 340px;
        #logo{
            transform: scale(0.8);
            transform-origin: center left;
        }
    }
    .headerTitles{
        transition: all 0.4s ease-in-out;
        border-bottom: 0.5px solid transparent;
        line-height: 12px;
        opacity: 1;
        &:hover{
            cursor: pointer;
            opacity: 0.8;
            color: $mainColor;
            border-color: $mainColor;
        }
    }
    .menuItem{
        display: flex;
        align-items: center;
        justify-content: center;
        @include media-breakpoint-down(xl) {
            display: none;
        }
    }
    
    .hiddenMenu{
        color: white;
        display: none;
        @include media-breakpoint-down(xl) {
            display: block;
            position: relative;
            .menuIcon{
                position: absolute;
                right: 40px;
                bottom: 50%;
                transform: translate(+50%, +50%) scale(1.6);
                cursor: pointer;
            }
            #hiddenMenuItem{
                position: absolute;
                top: $headerHeight;
                right: 0;
                width: 100vw;
                min-width: $minWidth;
                background-color: $mainColor;
                .hiddenHeaderTitles{
                    line-height: 50px;
                    font-size: 25px;
                    color: black;
                    border-bottom: 1px solid white;
                }
                .hiddenSearchBar{
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    border-bottom: 1px solid white;
                    border-top: 1px solid white;
                    .searchInput{
                        width: 75%;
                        color: black;
                        border: none;
                        border-bottom: 1px solid black;
                        background-color: transparent;
                        &:focus{
                            outline: none;
                        }
                    }
                    .searchIcon{
                        color: black;
                    }
                }
                
            }
        }
    }

    .searchBar{
        display: flex;
        justify-content: center;
        align-items: center;

        @include media-breakpoint-down(xl) {
        display: none;

        }
        .searchInput{
            width: 100px;
            color: black;
            border: none;
            border-bottom: 1px solid black;
            &:focus{
                outline: none;
            }
        }
    }
    
}
</style>