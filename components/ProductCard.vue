<template>
<<<<<<< HEAD
    <div class="charater-modal">
        <img class="img-container" src="@/assets/img/BGA1.jpg" alt="">
    </div>
    <NuxtLink to="/">
        <img class="max-w-[80%] mx-auto" src="@/assets/img/logoS.png" alt="">
    </NuxtLink>
    <div class="charater">
        <img class="w-[65%] mx-auto charater-img" :src="`${product.image}`" alt="">
        <h3 class="text-center text-[#fff] mt-1">{{ product.name }}</h3>
        <p class="text-center text-[yellow]">Rank: {{ product.rank }}</p>
            <NuxtLink :to="`/products/${product.id}`">
                 <button class="text-center w-full charater-btn">Chi Tiết</button>
            </NuxtLink>    
    </div>   
=======
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
  
                  
>>>>>>> 3141fb69ebe45d75d3854760c268a9c522cf42d3
</template>

<script setup>
    const {product} = defineProps(['product']);
    const xp = ref("red")
</script>

<style scoped>
    .charater-modal {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: -999;
        background: rgba(0, 0, 0, 0.4);
    }
    .img-container {
        position: absolute;
        z-index: -999;
        height: 100vh;
        width: 100%;
    }
    .charater {
        border: 1px solid #fff;
        border-radius: 12px;
        padding: 10px;
        background:  radial-gradient(rgba(255,255,255,0) 0, rgba(255,255,255,.15) 30%, rgba(255,255,255,.3) 32%, rgba(255,255,255,0) 33%) 0 0, radial-gradient(rgba(255,255,255,0) 0, rgba(255,255,255,.1) 11%, rgba(255,255,255,.3) 13%, rgba(255,255,255,0) 14%) 0 0, radial-gradient(rgba(255,255,255,0) 0, rgba(255,255,255,.2) 17%, rgba(255,255,255,.43) 19%, rgba(255,255,255,0) 20%) 0 110px, radial-gradient(rgba(255,255,255,0) 0, rgba(255,255,255,.2) 11%, rgba(255,255,255,.4) 13%, rgba(255,255,255,0) 14%) -130px -170px, radial-gradient(rgba(255,255,255,0) 0, rgba(255,255,255,.2) 11%, rgba(255,255,255,.4) 13%, rgba(255,255,255,0) 14%) 130px 370px, radial-gradient(rgba(255,255,255,0) 0, rgba(255,255,255,.1) 11%, rgba(255,255,255,.2) 13%, rgba(255,255,255,0) 14%) 0 0, linear-gradient(45deg, #343702 0%, #184500 20%, #187546 30%, #006782 40%, #0b1284 50%, #760ea1 60%, #83096e 70%, #840b2a 80%, #b13e12 90%, #e27412 100%);background-size: 470px 470px, 970px 970px, 410px 410px, 610px 610px, 530px 530px, 730px 730px, 100% 100%;background-color: #840b2a;
;
    }
    .charater-img {
        border-radius: 5px;
    }
    .charater-btn {
        padding: 10px;
        background-color: rgba(23, 23, 19, 0.8);
        color: #fff;
        border-radius: 25px;
        margin-top: 10px;
        transition: all 0.25s linear;
    }
    .charater-btn:hover {
        background-color: #fff;
        color: #000;
    }
</style>