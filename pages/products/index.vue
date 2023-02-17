<template>
<<<<<<< HEAD
    <h1 class="text-center text-[60px] pb-9 pt-8 text-[#fff] }}">Character</h1>
    <div class="px-[25px] grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3  xl:grid-cols-4 gap-6"> 
        <div v-for="(item, id) in products" :key="id">
                <ProductCard  :product = "item"/>
=======
    <h1 class="text-center my-[40px] font-roboto text-[80px]">SHOP</h1>
    <select v-model="bool" name="" id="">
        <option :value="true">
            true
        </option>
        <option :value="false">
            false
        </option>
    </select>
    <select v-model="big" name="" id="">
        <option :value="400">
            > 400
        </option>
        <option :value="200">
            > 200
        </option>
        <option :value="200">
            > 100
        </option>
        <option :value="0">
            defaut
        </option>
    </select>
    <select v-model="sortPrice" name="" id="">
        <option :value="true">
            price tăng dần
        </option>
        <option :value="false">
            price giảm dần
        </option>
    </select>
    <input class="inputItem" type="text" v-model="searchQuery">
    <template v-if="bool">
        <div class="grid grid-cols-4 gap-6">
        <template v-if="!pending" >
            <div lang="lazy" v-for="(item, id) in FilterItem" :key="id">
           <ProductCard  :product = "item"/>
>>>>>>> 3141fb69ebe45d75d3854760c268a9c522cf42d3
        </div>
    </div>
    </template>
    <template v-else>
        <div>ÍDSIDJSD</div>
    </template>
    

</template>

<script setup>
    import { ref } from 'vue';
    definePageMeta({
        layout: 'products'
    })
    const url = 'https://63ee0cf4d466e0c18ba84d91.mockapi.io/api/shopxp/Api/'
    //fetch the products
    //  const {data: products, pending, errors} = await useAsyncData("product_key", async () => {
    //      return $fetch(url)
    //  })
<<<<<<< HEAD
     const {data: products} = await useFetch('https://63ee0cf4d466e0c18ba84d91.mockapi.io/api/shopxp/Api/')
=======
    const {data: products} = await useFetch('https://63ee0cf4d466e0c18ba84d91.mockapi.io/api/shopxp/Api/')
>>>>>>> 3141fb69ebe45d75d3854760c268a9c522cf42d3
    useHead({
    title: 'Nuxt Dojo | Merch',
    meta: [
      { name: 'description', content: 'Nuxt 3 Merch'}
    ]
  })
  let bool = ref(true)
  let sortPrice = ref(true)
  let big = ref(0)
  let searchQuery = ref('')
  let FilterItem = computed(() => {
    let result = [...products.value];
    console.log(result)
        if (big.value > 0) {
            result = result.filter(item => (item.price > big.value))  
        }
        if (sortPrice.value) {
            result = result.sort((a, b) => parseFloat(a.price) - parseFloat(b.price));
        } else {
            result = result.sort((a, b) => parseFloat(b.price) - parseFloat(a.price));
        }
        result = result.filter(item => {
           return item.title.toLowerCase().includes(searchQuery.value.toLowerCase()) 
        })
        return result;
    })
    
    watch(sortPrice, (sortPrice) => {
        console.log(sortPrice)
    }) 
   
</script>

<style scoped>
   h1 {
    font-family: 'Dancing Script', cursive;
    font-weight: 700;
    position: relative;
   }
   h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }
    p {
        margin: 20px 0;
    }
    .inputItem {
        border: 1px solid red;   
    }
</style>