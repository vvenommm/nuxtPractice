<template>
  <div>
    <!-- CAR CARD -->
    <div
      class="relative shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px]"
      @click="navigateTo(`/car/${car.name}-${car.id}`)"
    >
      <img class="absolute w-7 right-5 top-2 z-20" :src="heartOutline" />
      <div class="flex h-full">
        <img :src="car.url" alt="" class="h-[200px]" />
        <div class="p-4 flex flex-col">
          <div>
            <h1 class="text-2xl text-blue-700">{{ car.name }}</h1>
            <p class="text-gray-700">{{ car.description }}</p>
          </div>
          <h1 class="mt-auto text-xl">${{ car.price }}</h1>
        </div>
      </div>
    </div>
    <!-- CAR CARD -->
  </div>
</template>

<script setup>
import heartFilled from '@/assets/heartFilled.png';
import heartOutline from '@/assets/heartOutline.png';

const props = defineProps({
  car: Object,
});
</script>

<style lang="scss" scoped></style>
