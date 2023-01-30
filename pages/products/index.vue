<template>
    <div class="grid grid-cols-4 gap-5">
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
    useHead({
    title: 'Nuxt Dojo | Merch',
    meta: [
      { name: 'description', content: 'Nuxt 3 Merch'}
    ]
  })
</script>

<style scoped>
   h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }
    p {
        margin: 20px 0;
    }
</style>