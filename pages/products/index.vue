<template>
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
        </div>
        </template>
        <ProductCard v-else>Processing...</ProductCard>
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
    const {data: products} = await useFetch('https://63ee0cf4d466e0c18ba84d91.mockapi.io/api/shopxp/Api/')
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
    .inputItem {
        border: 1px solid red;   
    }
</style>