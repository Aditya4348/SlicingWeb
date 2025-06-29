<script setup>
import { Container } from './layouts'
</script>

<template>
  <div class="w-full border-b border-gray-300">
    <Container class="flex justify-between items-center p-2">
      <h1 class="text-3xl font-bold text-[#ce4f0b]">Furnitures</h1>
      <ul class="flex space-x-4 font-semibold font-sans">
        <li><a href="#">Product</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Article</a></li>
        <li><a href="#">About Us</a></li>
      </ul>
      <div class="flex space-x-4">
        <a class="pi pi-shopping-bag rounded-full" style="font-size: 1.5rem" href="#"></a>
        <a class="pi pi-user rounded-full" style="font-size: 1.5rem" href="#"></a>
      </div>
    </Container>
  </div>
</template>
