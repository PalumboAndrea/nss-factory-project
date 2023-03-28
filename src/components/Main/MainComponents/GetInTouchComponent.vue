<script>

export default {
    name: "GetInTouchComponent",
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
    <div class="container-fluid position-relative p-0">
        <img :src="getImagePath('Rectangle 14.png')" alt="image" class="img-fluid">
        <div class="textContainer position-absolute top-50 start-50 translate-middle text-center py-4">
            <p class="mainTitle mb-0">
                Get in Touch
            </p>
            <p class="uppercaseTitle">
                discover more about news,
                <br>
                exclusive events and discount
            </p>
            <div class="mt-4">
                <input type="email" placeholder="Type your email">
                <button class="ms-1">
                    ok
                </button>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../../styles/general.scss" as *;

    .textContainer{
        color: white;
    }

    .uppercaseTitle{
        letter-spacing: 3px;
        font-size: 13px;
    }

    input{
        background-color: transparent;
        width: 80%;
        border: 1px solid rgba(255, 255, 255, 0.5);
        color: white;
        padding: 13px;
        &::placeholder{
            color: white;  
        }
        &:focus{
            outline: none;
        }
    }

    input[type="email"]{
        font-family: $titleFont;
    }

    button{
        font-family: $titleFont;
        color: white;
        background-color: transparent;
        border: 1px solid rgba(255, 255, 255, 0.5);
        padding: 13px;
    }


</style>