<script setup>
import { Navbar } from '../components'
import { img1, img2, img3, img4, img5 } from '@/assets/images'
import { logo1, logo2, logo3, logo4, logo5 } from '@/assets/images'
import { product1, product2, product3, product4 } from '@/assets/images'
import { CardProduct } from '../components/card'
import { Container } from '@/components/layouts'
import { products } from '@/assets/data/products'
import { TestimoniSection } from '@/views/section'
import { FooterSection, FooterSubcribe } from './section'

const images = [img1, img2, img3, img4, img5]
const logos = [logo1, logo2, logo3, logo4, logo5]

const ProductSales = [
  {
    image: img1,
    titleProduct: 'wall bookshelf',
  },
  {
    image: img2,
    titleProduct: 'unique bookshelf',
  },
  {
    image: img3,
    titleProduct: 'Group Sofa',
  },
]

const galleries = [
  {
    image: img1,
    title: 'wall bookshelf',
  },
  {
    image: img2,
    title: 'unique bookshelf',
  },
  {
    image: img3,
    title: 'Group Sofa',
  },
  {
    image: img4,
    title: 'wall bookshelf',
  },
  {
    image: img5,
    title: 'unique bookshelf',
  },
  {
    image: product1,
    title: 'Group Sofa',
  },
  {
    image: product2,
    title: 'Group produk',
  },
  {
    image: product3,
    title: 'Group produk',
  },
  {
    image: product4,
    title: 'Group produk',
  },
]

const buttons = [
  {
    icon: 'pi-shop',
    title: 'All',
  },
  {
    icon: 'pi-star-fill',
    title: 'Best Seller',
  },
  {
    icon: 'pi-tag',
    title: 'New',
  },
  {
    icon: 'pi-clock',
    title: 'Up coming',
  },
]

</script>


<template>
  <div>
    <Navbar />

    <div class="flex flex-col items-center space-y-5">
      <div class="md:space-y-10 space-y-5 max-w-4xl mx-auto mt-5">
        <h1 class="text-center md:text-7xl text-4xl font-medium">
          Transform Your Space, Elevate Your Style.
        </h1>
        <p class="text-center md:text-2xl text-lg">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, expedita?
        </p>
      </div>

      <div class="flex justify-center">
        <input
          type="text"
          class="w-full sm:min-w-[400px] h-[50px] py-2 px-3 bg-[#f5f5f5] rounded-l-md"
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
    <div class="flex flex-col items-center mt-10">
      <div class="flex space-x-6 mt-10">
        <div class="overflow-x-auto" v-for="gambar in images">
          <img :src="gambar" alt="gambar1" class="object-cover h-80 w-80" />
        </div>
      </div>

      <!-- Logo -->
      <div class="flex flex-wrap justify-center mt-4 space-x-4 space-y-4 md:space-x-8 md:space-y-0 w-full">
        <div class="mx-auto" v-for="logo in logos">
          <img :src="logo" alt="logo1" class="object-cover "/>
        </div>
      </div>
    </div>

    <!-- Card Product -->
    <div class="flex flex-col items-center space-y-2 my-10">
      <h1 class="text-3xl font-semibold text-gray-900">Crafted With Excellent Material</h1>
      <p class="md:text-lg text-sm text-gray-600">Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
    </div>
    <Container class="my-10 flex flex-wrap md:max-w-7xl justify-center space-x-3">
      <CardProduct
        v-for="product in products"
        :image="product.image"
        :title="product.title"
        :price="product.price"
        :discount="product.discount"
        :startingPrice="product.startingPrice"
      />
    </Container>

    <!-- Testimoni Section -->
    <TestimoniSection />

    <Container class="my-16 flex flex-wrap justify-center space-x-10 space-y-5">
      <div
        class="md:w-auto md:h-44 w-44 h-auto flex md:flex-row flex-col-reverse items-center md:space-x-10 justify-between bg-[#f5f5f5] md:p-6 p-3"
        v-for="Prod in ProductSales"
      >
        <div class="flex flex-col justify-center items-center space-y-2 w-full">
          <h1 class="text-xl font-semibold text-center text-gray-900">{{ Prod.titleProduct }}</h1>
          <button
            class="border border-[#d64d00] hover:border-[#ce380b] text-[#d64d00] font-semibold py-2 px-3 rounded-md cursor-pointer"
          >
            Shop Now
          </button>
        </div>
        <img :src="Prod.image" alt="" class="md:w-1/2 w-full h-full object-cover" />
      </div>
    </Container>

    <section class="w-full min-h-screen">
      <Container class="flex flex-col items-center space-y-4 pt-10">
        <h1 class="text-3xl font-bold font-sans">Our Furnitures Gallery</h1>
        <p class="text-md text-center text-gray-500">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Soluta, tempore.<br />
        </p>
        <div class="flex items-center space-x-2">
          <button
            class="border border-gray-900 hover:border-blue-700 hover:bg-blue-200 text-black hover:text-blue-950 py-2 px-3 rounded-full cursor-pointer flex items-center space-x-2"
            v-for="button in buttons"
          >
            <span :class="`pi ${button.icon} text-lg`"></span>
            <span class="font-semibold">{{ button.title }}</span>
          </button>
        </div>
        <div class="columns-2 md:columns-3 gap-4 p-4">
          <div
            v-for="gallery in galleries"
            class="mb-4 break-inside-avoid overflow-hidden rounded-md shadow-md"
          >
            <img :src="gallery.image" alt="gambar gallery" class="w-full object-cover rounded" />
          </div>
        </div>
      </Container>
    </section>

    <FooterSubcribe />
    <FooterSection />
  </div>
</template>
