<template>
  <div>
    <!-- CAR HERO -->
    <div class="mt-10 items-center">
<<<<<<< HEAD
      <img
        src="https://file.kelleybluebookimages.com/kbb/base/evox/CP/15180/2023-Chevrolet-Corvette-front_15180_032_1838x654_GA7_cropped.png"
        alt=""
        class="h-[100px]"
      />
=======
      <img :src="car.url" alt="" class="h-[100px]" />
>>>>>>> de05561 (에러 페이지, 데이터 연결)
      <h1 class="mt-10 text-4xl">{{ car.name }}</h1>
      <div
        class="text-slate-500 flex text-lg mt-3 border-b pb-5 justify-between"
      >
<<<<<<< HEAD
        <div v-for="feature in features" :key="feature" class="flex">
          <p class="mr-2">{{ feature }}</p>
=======
        <div class="flex">
          <p class="mr-2">{{ car.seats }} seats</p>
          <p class="mr-2"></p>
          <p class="mr-2">{{ car.miles }} miles</p>
>>>>>>> de05561 (에러 페이지, 데이터 연결)
        </div>
        <div>
          <p class="font-bold text-2xl">${{ car.price }}</p>
        </div>
      </div>
    </div>
    <!-- CAR HERO -->
  </div>
</template>

<script setup>
const props = defineProps({
  car: Object,
});
</script>

<style lang="scss" scoped></style>
