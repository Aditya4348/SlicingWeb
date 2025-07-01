<script setup>
import { Container } from '@/components/layouts'
import { CommentarCard } from '@/components/card'
import testimonis from '@/assets/data/testimoni';

</script>

<template>
  <section class="my-10 w-full min-h-[50vh] space-y-10 bg-[#f5f5f5] overflow-x-hidden py-5">
    <Container class="flex flex-col items-center space-y-4 pt-14">
      <h1 class="md:text-3xl text-2xl font-bold font-sans">What Our Customers Say</h1>
      <p class="md:text-md text-sm text-center text-gray-500 md:w-auto w-3/4">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Soluta, tempore.</p>
    </Container>
    <div class="overflow-hidden w-full">
      <div class="flex space-x-6 p-4 animate-marquee">
          <CommentarCard 
            v-for="testimoni in testimonis" 
            :testimoni="testimoni.testimoni"
            :name="testimoni.name"
            :profil="testimoni.profil"
          />
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes marquee {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50%);
  }
}
.animate-marquee {
  animation: marquee 10s linear infinite;
}

</style>
