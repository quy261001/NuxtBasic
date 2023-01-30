<template>
     <header class="shadow-sm bg-white">
        <nav class="container mx-auto p-4 flex items-center justify-between">
            <NuxtLink to="/" class="font-bold text-[40px]">NuxtJS</NuxtLink> 
            <ul class="flex gap-4 text-[18px]">    
                <li><NuxtLink to="/">Home</NuxtLink></li>
                <li><NuxtLink to="/products">Products</NuxtLink></li> 
            </ul>
        </nav>
    </header>

    <!-- Content Products -->
    <div class="container mx-auto p-4">
        <slot />
    </div>
</template>

<script setup>

</script>

<style scoped>
     .router-link-exact-active {
        color: #12b488;
    }
</style>