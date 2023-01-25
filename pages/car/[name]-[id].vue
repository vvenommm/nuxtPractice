<template>
  <div>
    <!-- <NavBar /> layouts 만든 후에 주석 처리 -->

    <!-- CAR DETAIL PAGE -->
    <div
      v-if="car"
      class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-4/5"
    >
      {{ car }}
      <!-- CAR HERO -->
      <CarDetailHero :car="car" />
      <!-- CAR HERO -->

      <!-- CAR ATTRIBUTE -->
      <CarDetailAttributes :features="car.features" />
      <!-- CAR ATTRIBUTE -->

      <!-- CAR DESCRIPTION -->
      <CarDetailDescription :description="car.description" />
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
const { cars } = useCars();

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

const car = computed(() => {
  return cars.find((c) => {
    return c.id === parseInt(route.params.id);
  });
});

// custom error
if (!car.value) {
  throw createError({
    statusCode: 404,
    message: `Car with ID of ${route.params.id} does not exist`,
  });
}
</script>

<style lang="scss" scoped></style>
