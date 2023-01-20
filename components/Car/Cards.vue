<template>
  <div>
    <!-- CAR CARDS -->
    <div class="w-full">
      <!-- CAR CARD -->
      <CarCard v-for="car in cars" :key="car.id" :car="car" />
      <!-- CAR CARD -->
    </div>
    <!-- CAR CARDS -->
  </div>
</template>

<script setup>
const { cars } = useCars();
</script>

<style lang="scss" scoped></style>
