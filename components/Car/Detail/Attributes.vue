<template>
  <div>
    <!-- CAR ATTRIBUTE -->
    <div class="mr-10 mt-5 border-b pb-5">
      * 그냥 features로 해도 출력 됨. props.features로 안 해도 됨
      <div v-for="feature in features" :key="feature" class="flex text-lg mt-2">
        <p class="rounded text-lime-800 mr-3">♬</p>
        <p class="rounded text-lime-800 mr-3">{{ feature }}</p>
      </div>
    </div>
    <!-- CAR ATTRIBUTE -->
  </div>
</template>

<script setup>
const props = defineProps({
  features: Array,
});
</script>

<style lang="scss" scoped></style>
