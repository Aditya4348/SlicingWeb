<script setup>
import { Sofa, male, kutip } from '@/assets/images'
import { Container } from '@/components/layouts'

const testimonial = [
  {
    testimoni: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, debitis.',
    name: 'John Doe',
    profil: male,
  },
]
</script>

<template>
  <footer class="relative">
    <!-- Tertimonial Footer -->
    <section class="w-full min-h-[70vh] bg-[#F5F5F5] py-10 mt-10">
      <Container class="flex items-start space-x-10 relative">
        <!-- Testimonial dengan efek tangga -->
        <div
          class="flex flex-col min-w-[500px] h-auto rounded-lg space-y-4"
          v-for="(testimoni, index) in testimonial"
          :key="index"
          :style="`margin-top: ${index * 40}px`"
        >
          <div class="flex items-center space-x-2">
            <img :src="testimoni.profil" alt="User" class="w-16 h-16 rounded-full object-cover" />
            <div>
              <h2 class="text-lg font-semibold text-gray-800">{{ testimoni.name }}</h2>
              <p class="text-sm text-gray-500">Customer</p>
            </div>
          </div>
          <p class="text-gray-700 text-sm font-normal font-sans">
            {{ testimoni.testimoni }}
          </p>
          <div class="flex items-center space-x-4">
            <div class="flex justify-between items-center w-full">
              <div class="flex items-center space-x-1 mt-2">
                <span class="pi pi-star-fill text-amber-500" v-for="i in 5" :key="i"></span>
              </div>
            </div>
          </div>
        </div>

        <!-- Komponen Kutip -->
        <kutip 
        class="mt-[100px]"
        />

        <!-- Deskripsi Akhir -->
        <div class="flex w-[20%] flex-col space-y-4 mt-[160px]">
          <h1 class="text-4xl font-semibold font-sans text-black">Our Furniture Review</h1>
          <p class="text-[#505050] text-sm font-normal font-sans">
            Lorem Ipsum is simply dummy text of the printing and typesetting industry.
          </p>
        </div>
      </Container>
    </section>

    <!-- Footer Subcribe -->
    <section class="w-full min-h-[30vh] relative bg-[#F2A156] py-10">
      <Container class="w-[60%] flex items-center space-y-4 p-5">
        <div class="w-[40%]">
          <h1 class="text-2xl font-light font-sans text-white">
            Subscribe to get attractive offers on our products
          </h1>
        </div>
        <div class="flex justify-center w-[60%]">
          <div class="flex justify-center w-full py-4 pr-4 pl-6 bg-[#f5f5f5]">
            <input
              type="text"
              class="w-[70%] h-[50px] outline-none border-none py-2 px-3 rounded-l-md"
              placeholder="Enter your email address"
            />
            <button
              class="w-[30%] bg-[#5C59D4] hover:bg-[#4f4bcb] text-white font-semibold py-2 px-3 cursor-pointer"
            >
              Subscribe
            </button>
          </div>
        </div>
      </Container>
    </section>

    <!-- Image Sofa -->
    <img :src="Sofa" alt="" class="w-1/2 object-cover absolute top-[30%] -left-30" />
  </footer>
</template>
