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
      <NuxtErrorBoundary>
        <!-- CAR SIDE BAR -->
        <CarSideBar />
        <!-- CAR SIDE BAR -->

        <!-- CAR CARD -->
        <NuxtPage />
        <!-- CAR CARD -->
        <template #error="{ error }">
          <div class="text-center mx-auto flex flex-col">
            <h1 class="text-5xl text-red-600 mb-4">
              Sorry, Something went wrong~
            </h1>
            <code>{{ error }}</code>
            <button
              class="text-white bg-blue-400 px-10 py-3 rounded mt-4"
              @click="error.value = null"
            >
              Go Back
            </button>
          </div>
        </template>
      </NuxtErrorBoundary>
      <!-- 에러 발생하면 내부 컴포넌트 렌더링 X -->
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
