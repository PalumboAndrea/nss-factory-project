<script>
export default {
    name: "HeaderComponent",
    data() {
        return {
            headerMenuTitles: ['Abous Us', 'Brands', 'Projects', 'Magazine', 'Press', 'Contacts']
        }
    },
}
</script>

<template>
    <div id="header-container" class="container-fluid p-0 sticky-top">
        <div class="row h-100 g-0">
            <div class="col-3 d-flex align-items-center headerTitle">
                <div class="logoContainer ps-3 d-flex align-items-center">
                    <img src="../assets/imgs/logo.png" alt="logo" id="logo">
                </div>
            </div>
            <div class="col-7">
                <div class="row h-100 g-0">
                    <div class="col d-flex flex-column align-items-center justify-content-center menuItem" v-for="headerMenuTitle in headerMenuTitles">
                        <span class="headerTitles">
                            {{ headerMenuTitle }}
                        </span>
                    </div>
                </div>
            </div>
            <div class="col p-0 d-flex align-items-center justify-content-end pe-3">
                <input type="text" class="searchInput me-1 p-0 m-0">
                <font-awesome-icon :icon="['fas', 'magnifying-glass']"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss" as *;

#header-container{
    height: $headerHeight;
    background-color: white;
    .headerTitle{
        
        color: white;
        text-transform: uppercase;
        .logoContainer{
            background-color: $mainColor;
            height: 100%;
            width: 340px;
            #logo{
                height: 43px;
                width: 292px;
            }
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
</style>