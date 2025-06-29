<script setup>
import { img1 } from '@/assets/images'

const props = defineProps({
    image: {
        type: String,
        default: img1
    },
    title: {
        type: String,
        default: 'Product Name'
    },
    price: {
        type: String,
        default: ''
    },
    startingPrice: {
        type: String,
        default: ''
    },
    discount: {
        type: String,
        default: null
    }
})

</script>

<template>
    <div class="w-[300px] h-[400px] rounded-xl shadow-md flex flex-col items-center p-4 space-y-2">
    
    <!-- Gambar dan Judul Singkat -->
    <div class="w-full h-[85%] bg-[#f5f5f5] relative flex flex-col items-center justify-center space-y-2">
      <img :src="props.image" alt="Produk" class=" w-4/5 h-[70%] object-cover rounded-md" />
      <span v-if="props.discount" class="text-xs font-semibold absolute top-0 left-0 bg-[#d64d00] text-white px-2 py-0.5 rounded-full">{{ props.discount }}</span>
      <a href="#" class="text-sm font-semibold text-center text-red-600 flex items-center justify-center space-x-1">
        <span class="pi pi-shopping-cart" style="font-size: 1.2rem"></span>
        <span>Add to Cart</span>
      </a>
    </div>
    
    <!-- Detail Produk -->
    <div class="w-full flex flex-col justify-center">
      <h1 class="text-xl font-semibold text-gray-900">{{ props.title }}</h1>
      <div class="flex items-center space-x-2">
        <span v-if="props.startingPrice" class="text-sm font-normal text-gray-700 line-through">${{ props.startingPrice  }}</span>
        <p class="text-md font-medium text-black">${{ props.price }}</p>
      </div>
    </div>

  </div>
</template>
