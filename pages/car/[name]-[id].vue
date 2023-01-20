<template>
  <div>
    <!-- <NavBar /> layouts 만든 후에 주석 처리 -->

    <!-- CAR DETAIL PAGE -->
    <div
      class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-4/5"
    >
      <!-- CAR HERO -->
      <CarDetailHero />
      <!-- CAR HERO -->

      <!-- CAR ATTRIBUTE -->
      <CarDetailAttributes />
      <!-- CAR ATTRIBUTE -->

      <!-- CAR DESCRIPTION -->
      <CarDetailDescription />
      <!-- CAR DESCRIPTION -->

      <!-- CAR CONTACT -->
      <CarDetailContact />
      <!-- CAR CONTACT -->
    </div>
    <!-- CAR DETAIL PAGE -->
  </div>
</template>

<script setup>
const route = useRoute();

const { toTitleCase } = useUtilities();
useHead({
  title: toTitleCase(route.params.name),
});

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
