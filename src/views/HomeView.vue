<script setup>
import { Navbar } from '../components'
import { img1, img2, img3, img4, img5 } from '@/assets/images'
import { logo1, logo2, logo3, logo4, logo5 } from '@/assets/images'
import { CardProduct } from '../components/card'
import { Container } from '@/components/layouts'
import { products } from '@/assets/data/products'
import { TestimoniSection } from '@/views/section'

const images = [img1, img2, img3, img4, img5]
const logos = [logo1, logo2, logo3, logo4, logo5]


</script>

<template>
  <div>
    <Navbar />

    <div class="space-y-10 max-w-4xl mx-auto mt-5">
      <h1 class="text-center text-7xl font-medium">Transform Your Space, Elevate Your Style.</h1>
      <p class="text-center text-2xl">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, expedita?
      </p>

      <div class="flex justify-center">
        <input
          type="text"
          class="min-w-[400px] h-[50px] py-2 px-3 bg-[#f5f5f5] rounded-l-md"
          placeholder="Enter your email address"
        />
        <button
          class="bg-[#d64d00] hover:bg-[#ce380b] text-white py-2 px-3 rounded-r-md cursor-pointer"
        >
          Search
        </button>
      </div>
    </div>

    <!-- Gambar -->
    <div class="flex space-x-6 mt-10">
      <div class="overflow-x-auto" v-for="gambar in images">
        <img :src="gambar" alt="gambar1" class="object-cover h-80 w-80" />
      </div>
    </div>

    <!-- Logo -->
    <div class="flex justify-between mt-4">
      <div class="mx-auto" v-for="logo in logos">
        <img :src="logo" alt="logo1" class="object-cover" />
      </div>
    </div>

    <!-- Card Product -->
    <Container class="my-10 flex flex-wrap justify-center space-x-3">
      <CardProduct 
      v-for="product in products"
      :image="product.image"
      :title="product.title"
      :price="product.price"
      :discount="product.discount"
      :startingPrice="product.startingPrice"
      />
    </Container>

    <TestimoniSection></TestimoniSection>
  </div>
</template>
