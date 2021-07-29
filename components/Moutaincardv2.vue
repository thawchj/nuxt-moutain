<template>
    <div class="my-container">
        <nuxt-link :to="`/${id}`">
            <div class="img-container">
                <img class="moutain-img" :src="image" 
                width="100%" height="auto">
                <div class="black-cover"></div>
            </div>
        </nuxt-link>
        <div class="moutaincard-name">{{name}}</div>
        <div class="moutaincard-info">
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        </div>
    </div>   
</template>
<script>
export default {
props:{
        id:{
            type: Number,
            default: 0
        },
        image:{
            type: String,
            default: ''
        },
        name:{
            type: String,
            default: '' 
        },
    }
}
</script>

<style scoped>
.my-container{
    background-color: rgb(255, 255, 255);
    box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.425);
}
.moutaincard-name{
    padding: 15px;
    font-size: 21px;
    font-weight: bold;
    color: rgb(49, 49, 49);
}
.moutaincard-info{
    padding: 0px 10px 10px 15px;
    color: rgb(49, 49, 49);
}
</style>