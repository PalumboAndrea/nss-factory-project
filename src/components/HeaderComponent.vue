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
        <div class="row h-100">
            <div class="col-2 ps-4 d-flex align-items-center headerTitle">
                watch/lab
            </div>
            <div class="col-8 d-flex align-items-center">
                <div class="container">
                    <div class="row">
                        <div class="col d-flex justify-content-center menuItem" v-for="headerMenuTitle in headerMenuTitles">
                            {{ headerMenuTitle }}
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-2 d-flex justify-content-end pe-4 d-flex align-items-center">
                Searchbar
            </div>
        </div>
        

    </div>
</template>

<style lang="scss">
@use "../styles/general.scss" as *;

#header-container{
    height: $headerHeight;

    .headerTitle{
        background-color: $mainColor;
        color: white;
        text-transform: uppercase;
    }

    .menuItem{
        transition: 0.3s;
        &:hover{
            transition: 0.3s;
            cursor: pointer;
            color: $mainColor;
            text-decoration: underline;
        }
    }

}




</style>