<template>
    <header class="shadow-sm bg-white">
        <nav class="container mx-auto p-4 flex items-center justify-between">
            <NuxtLink to="/">
                <img class="w-[10%]" src="http://mauweb.monamedia.net/bitis/wp-content/uploads/2018/03/logo-mona.png" alt="">
            </NuxtLink> 
            <ul class="Nav flex gap-4 text-[14px] text-[#111] font-roboto uppercase font-bold">    
                <li><NuxtLink to="/">Home</NuxtLink></li> 
                <li><NuxtLink to="/about">About</NuxtLink></li>
                <li><NuxtLink to="/products">products</NuxtLink></li>
            </ul>
        </nav>
    </header>
    <!-- Content -->
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
    .Nav {
        font-family: 'Roboto', sans-serif;
    }
</style>