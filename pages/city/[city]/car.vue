<template>
  <div>
    <div>
      여기는 city/[city]/car.vue이고 [[make]].vue에 carCard만 남기고 다 지움
    </div>
    <!-- <NavBar /> layouts 만든 후에 주석 처리 -->

    <!-- CARS PAGE -->
    <!-- <div
      class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-4/5"
    > -->
    <div class="mt-32 flex">
      <!-- CAR SIDE BAR -->
      <CarSideBar />
      <!-- CAR SIDE BAR -->

      <!-- CAR CARD -->
      <NuxtPage />
      <!-- CAR CARD -->
    </div>
    <!-- </div> -->
    <!-- CARS PAGE -->
  </div>
</template>

<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();
useHead({
  title: `${
    route.params.make ? toTitleCase(route.params.make) : 'Cars'
  } in ${toTitleCase(route.params.city)}`,
});

// useUtilities.js로 옮김
// function toTitleCase(str) {
//   return str.replace(/\w\S*/g, function (txt) {
//     return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
//   });
// }

definePageMeta({
  layout: 'custom',
});
</script>

<style lang="scss" scoped></style>
