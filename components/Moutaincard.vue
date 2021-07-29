<template>
    <div class="my-container">
        <nuxt-link :to="`/${id}`">
            <div class="img-container">
                <img class="moutain-img" :src="image" 
                width="100%" height="auto">
                <div class="moutain-in">{{name}}</div>
                <div class="black-cover"></div>
            </div>
        </nuxt-link>
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
        }
    }
}
</script>
<style scoped>
.my-container{
    background-color: rgb(209, 208, 208);
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.603);
    
}
.img-container{
    position: relative;
    
}
.moutain-in{
    position: absolute;
    z-index: 2;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
    font-size: 20px;
    font-weight: bold;
}
.black-cover{
    background-color: rgba(0, 0, 0, 0.288);
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: 1;
    
    
}


</style>