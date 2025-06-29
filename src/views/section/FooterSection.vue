<script setup>
import { Container } from '@/components/layouts'

const footersMenu = [
  {
    menu: 'Categories',
    items: ['Living Room', 'Bed Room', 'Kitchen', 'Bath Room'],
  },
  {
    menu: 'Populer Product',
    items: ['Single Sofa Black', 'Wooden Bookcase', 'Wooden Chair', 'Luxury White Bed'],
  },
  {
    menu: 'Sitemap',
    items: ['Product', 'Services', 'Article', 'About Us'],
  },
  {
    menu: 'Follow Us',
    items: ['Facebook', 'Instagram', 'TikTok', 'Youtube'],
  },
]
</script>

<template>
  <section class="w-full min-h-[50vh] bg-[#5C59D4] py-10">
    <Container class=" flex flex-col items-center space-y-4">
      <div class="flex items-center space-y-10 space-x-20 w-full">
        <div class="flex flex-col space-y-2 w-[15%]">
          <h1 class="text-5xl font-bold text-white">LOGO</h1>
          <p class="text-sm text-[#F5F5F5]">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Mollitia, quaerat!
          </p>
        </div>
        <div class="flex cursor-default justify-between space-x-20 w-[75%]">
          <div class="flex flex-col space-y-2" v-for="menu in footersMenu">
            <h1 class="text-xl font-semibold text-white">{{ menu.menu }}</h1>
            <ul class="flex flex-col space-y-2 text-sm text-[#F5F5F5]">
              <li v-for="item in menu.items">
                {{ item }}
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="flex items-center space-x-4 w-full border-t border-t-gray-600 p-3">
        <span class="text-sm text-white"> © 2025 by Aditya Alfitorin. All rights reserved </span>
      </div>
    </Container>
  </section>
</template>
