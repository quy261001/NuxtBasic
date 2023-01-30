<template>
        <div class="card text-center">
            <img :src="product.image" alt="" class="h-[120px] max-w-[70%] my-[0] mx-auto">
            <p class="font-bold text-gray-500 m-4 truncate">{{ product.title }}</p>
            <p class="font-bold text-gray-500 m-4 truncate">Price: {{ product.price }}$</p>
            <NuxtLink :to="`/products/${product.id}`">
                <p class="btn my-4">View Details</p>
            </NuxtLink>
        </div>

</template>

<script setup>
    const {product} = defineProps(['product']);
</script>

<style scoped>

</style>