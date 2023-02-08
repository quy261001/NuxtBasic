<template>
    <h1 class="text-center my-[40px] font-roboto text-[80px]">SHOP</h1>
    <div class="grid grid-cols-4 gap-6">
        <div v-for="(item, id) in products" :key="id">
           <ProductCard :product = "item"/>
        </div>
    </div>
</template>

<script setup>
    definePageMeta({
        layout: 'products'
    })
    // fetch the products
    const {data: products} = await useFetch('http://localhost:3000/products')
    // async fetch() {
    //     const {data: products} = await useFetch('http://localhost:3000/products')
    // }   
    useHead({
    title: 'Nuxt Dojo | Merch',
    meta: [
      { name: 'description', content: 'Nuxt 3 Merch'}
    ]
  })
</script>

<style scoped>
   h1 {
    font-family: 'Dancing Script', cursive;
    font-weight: 700;
    position: relative;
   }
   h1::before {
    position: absolute;
    content: '';
    border-bottom: 2px solid #eee;
    width: 100%;
    left: 0;
    bottom: 0;
   }
   h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }
    p {
        margin: 20px 0;
    }
</style>