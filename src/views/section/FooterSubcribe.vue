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
    <section class="w-full min-h-[70vh] bg-[#F5F5F5] md:py-10 mt-10">
      <Container
        class="flex md:flex-row flex-col-reverse md:items-start space-x-10 relative gap-5 py-4 px-2"
      >
        <!-- Testimonial dengan efek tangga -->
        <div class="flex md:flex-row flex-col-reverse space-y-4">
          <div
            class="flex flex-col min-w-[500px] h-auto rounded-lg md:space-y-4 space-y-2"
            v-for="(testimoni, index) in testimonial"
            :key="index"
            :style="`margin-top: ${index * 40}px`"
          >
            <div class="flex items-center space-x-2">
              <img :src="testimoni.profil" alt="User" class="md:w-16 md:h-16 w-10 h-10 rounded-full object-cover" />
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
          <div class="flex items-center md:justify-center justify-end absolute right-[10%] top-[50%] md:static">
            <kutip class="md:mt-[100px] md:w-[60%] w-[20%]" />
          </div>
        </div>

        <!-- Deskripsi Akhir -->
        <div class="flex md:w-[20%] w-[50%] flex-col md:space-y-4 space-y-2 md:mt-[160px]">
          <h1 class="md:text-4xl text-3xl font-bold font-sans text-black">
            Our Furniture Review
          </h1>
          <p class="text-[#505050] text-sm font-normal font-sans">
            Lorem Ipsum is simply dummy text of the printing and typesetting industry.
          </p>
        </div>
      </Container>
    </section>

    <!-- Footer Subcribe -->
    <section class="w-full min-h-[30vh] relative bg-[#F2A156] md:py-10 pt-10 pb-5">
      <Container class="md:w-[60%] w-[80%] flex md:flex-row flex-col items-center  space-y-4 p-5">
        <div class="md:w-[40%] w-full">
          <h1 class="text-2xl font-light font-sans text-white">
            Subscribe to get attractive offers on our products
          </h1>
        </div>
        <div class="flex justify-center md:w-[60%] w-full">
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
    <img :src="Sofa" alt="" class="md:w-1/2 w-full object-cover absolute sm:top-[30%] top-[40%] -left-30" />
  </footer>
</template>
