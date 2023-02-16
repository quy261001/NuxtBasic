<template>
        <div class="card-main__detail">
        <div class="basicInfo">
            <div class="card-container-main">
              <div class="images">
                <div class="img">
                    <div class="item">
                        <img :src="`${product.image}`">
                    </div>
                </div>
            </div>
            <div class="content-right">
              <div class="title flex items-center flex-col gap-3">
                <div class="name text-[14px]">{{ product.title }}</div>
                <div class="category w-[100%] text-[18px]">
                  {{ product.category }}</div>
            </div>
            </div>
            </div>
            <NuxtLink :to="`/products/${product.id}`">
                <div class="addCard">
                    <i class="material-icons">shopping_bag</i>
                </div>
            </NuxtLink>
           
        </div>
        <div class="mores">
            <div class="stars ">
               <p class="flex items-center gap-1 text-[#eee] text-[20px]">Rate: {{ product.rating.rate }} 
                <i class="material-icons text-[#FFFF33]">star</i>
              </p>
            </div>
            <div class="price text-[20px] text-[#3BE798]">Price: {{ product.price }}$</div>
        </div>
        </div> 
  
                  
</template>

<script setup>
    const {product} = defineProps(['product']);
    const xp = ref("red")
</script>

<style scoped>
i.star-icon {
  color: yellow;
  font-size: 27px;
}
.card-main__detail{
    border-radius: 30px;
    width:100%;
    background-color: #2B2B2B;
}
.card-container-main {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;
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
    text-align: center;
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
    margin-bottom: 30px;
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
    padding:25px 25px;
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
    right:46%;
    bottom:-25px;
    border:5px solid #2B2B2B;
    transition: 0.5s;
    opacity: 0;
    transform: translate(-50%,10px);
}

/* animation */
.card-main__detail:hover .img img{
    transform: scale(1.1);
}
.card-main__detail:hover .img::after{
    height:60px;

}
.card-main__detail:hover .addCard i,
.card-main__detail:hover .addCard::before,
.card-main__detail:hover .addCard::after{
    opacity: 1;
    transform: translate(-46%,0);
    cursor: pointer;
}
</style>