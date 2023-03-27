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
    <div id="header-container" class="container-fluid p-0">
        <div class="row h-100 px-2">
            <div class="col-2 d-flex align-items-center headerTitle">
                watch/lab
            </div>
            <div class="col-8 d-flex align-items-center p-0">
                <div class="container">
                    <div class="row">
                        <div class="col d-flex flex-column align-items-center justify-content-center menuItem" v-for="headerMenuTitle in headerMenuTitles">
                            <span class="title">
                                {{ headerMenuTitle }}
                            </span>
                            
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-2 p-0">
                Searchbar
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss" as *;

#header-container{
    height: $headerHeight;
    .headerTitle{
        background-color: $mainColor;
        color: white;
        text-transform: uppercase;  
    }
    .title{
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
}
</style>