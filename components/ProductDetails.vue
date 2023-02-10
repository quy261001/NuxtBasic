<template>
    <div class="card-main__detail">
        <div class="basicInfo">
            <div class="card-container">
              <div class="images">
                <div class="img">
                    <div class="item">
                        <img :src="`${productDetai.image}`">
                    </div>
                </div>
            </div>
            <div class="content-right max-w-[50%]">
              <div class="title flex items-center flex-col gap-3">
                <div class="name text-[26px]">{{ productDetai.title }}</div>
                <div class="category text-[20px]">
                  {{ productDetai.category }}</div>
                <div class="info text-[20px]">{{ productDetai.description }}</div>
            </div>
            </div>
            </div>
            <div class="addCard">
                <i class="material-icons">add_shopping_cart</i>
            </div>
            
        </div>
        <div class="mores">
            <div class="stars ">
               <p class="flex items-center gap-1 text-[#eee] text-[20px]">Rate: {{ productDetai.rating.rate }} 
                <span class="material-icons text-[#FFFF33]">star</span>
              </p>
            </div>
            <div class="price text-[20px] text-[#3BE798]">Price: {{ productDetai.price }}$</div>
        </div>
    </div>

</template>

<script setup>

const {productDetai} = defineProps(['productDetai']);
</script>

<style scoped>
:root{
    --green: #3BE798;
    --violet: #7F6EB2;
    --dark: #2B2B2B;
}
i.star-icon {
  color: yellow;
}
.card-main__detail{
    position: absolute;
    top:50%;
    left:50%;
    border-radius: 30px;
    transform: translate(-50%,-50%);
    width:1000px;
    background-color: #2B2B2B;
}
.card-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.basicInfo{
    background-color: #f5f5f5;
    border-radius: 30px;
    padding:25px 40px 50px 40px;
    position: relative;
}
.title .category,
.title .info{
    font-weight: 600;
    font-family: 'Dancing Script', cursive;
    display: -webkit-box;
    -webkit-line-clamp:10;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
.title .name{
    font-weight: bold;
    font-family: 'Pacifico', cursive;
    padding-bottom:3px;
}
.name {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;  
  overflow: hidden;
}
.card-main__detail .img{
    position: relative;
    z-index: 1;
    text-align: center;
}
.card-main__detail .img img{
    width:200px;
    transform: scale(1);
    transition: 0.5s;
}
.img input{
    position: absolute;
    opacity: 0;
}
.colors{
    display: flex;
    font-size: xx-small;
    text-align: center;
    margin-left: 45px;
    gap: 10px;
}
.colors label{
    margin-right:10px;
}
.colors .name{
    margin-bottom:5px;
}
.colors .ellipse{
    width:40px;
    height:40px;
    border-radius: 50%;
    cursor: pointer;
}
.mores{
    padding:25px 94px;
}
.mores .stars,
.mores .price{
    display: inline-block;
}
.mores .price{
    float: right;
    font-weight: 600;
    letter-spacing: 1px;
    font-family: 'Dancing Script', cursive;
}
.mores .stars{
    color:#9b9a9a;
    font-family: 'Dancing Script', cursive;
}
.text-yellow{
    color:rgb(209, 209, 6);
}
.addCard{
    position: absolute;
    width:100%;
    bottom:0;
}
.addCard i{
    position: absolute;
    width:50px;
    height:50px;
    background-color: #3BE798;
    color:#222;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    right:16%;
    bottom:-25px;
    border:5px solid #2B2B2B;
    transition: 0.5s;
    opacity: 0;
    transform: translate(0,10px);
}

/* animation */
.card-main__detail:hover .img img{
    transform: scale(1.2);
}
.card-main__detail:hover .img::after{
    height:60px;

}
.card-main__detail:hover .addCard i,
.card-main__detail:hover .addCard::before,
.card-main__detail:hover .addCard::after{
    opacity: 1;
    transform: translate(0,0);
    cursor: pointer;
}
</style>