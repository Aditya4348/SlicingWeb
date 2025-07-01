<script setup>
const props = defineProps({
    testimoni: {
        type: String,
        default: ''
    },
    name: {
        type: String,
        default: ''
    },
    profil: {
        type: String,
        default: ''
    }
})
</script>

<template>
  <div class="flex flex-col min-w-[400px]  h-auto bg-white shadow-lg rounded-lg p-8 space-y-4">
    <div class="flex items-center space-x-2">
      <span class="pi pi-bookmark-fill text-gray-600"></span>
      <span class="text-gray-500 text-sm">Testimoni</span>
    </div>
    <p class="text-gray-700 text-lg font-medium">
      {{ props.testimoni }}
    </p>
    <div class="flex items-center space-x-4">
      <img
        :src="props.profil"
        alt="User"
        class="w-16 h-16 rounded-full object-cover"
      />
      <div class="flex justify-between items-center w-full">
        <div>
          <h2 class="text-lg font-semibold text-gray-800">{{ props.name }}</h2>
          <p class="text-sm text-gray-500">Customer</p>
        </div>
        <div class="flex items-center space-x-1 mt-2">
          <span class="pi pi-star-fill text-amber-500" v-for="i in 5"></span>
        </div>
      </div>
    </div>
  </div>
</template>

