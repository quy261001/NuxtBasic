<template>
     <header class="shadow-sm bg-white">
        <nav class="container mx-auto p-4 flex items-center justify-between">
            <NuxtLink to="/"> <img class="w-[10%]" src="http://mauweb.monamedia.net/bitis/wp-content/uploads/2018/03/logo-mona.png" alt=""></NuxtLink> 
            <ul class="flex gap-4 text-[24px] font-bold w-[40%]">
                <li><NuxtLink to="/" class="flex items-center gap-1"><i class="material-icons text-[24px]">arrow_back</i> Back To Home</NuxtLink></li>        
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