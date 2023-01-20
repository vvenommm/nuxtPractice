<template>
  <div>
    <!-- HOME SEARCH BAR -->
    <div
      class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
    >
      <input
        type="text"
        class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
        v-model="city"
        :class="cityError ? 'border-red-500 border' : ''"
        placeholder="Search by city..."
      />
      <button class="bg-sky-500 px-10 text-white" @click="handleSearch">
        Search
      </button>
    </div>
    <!-- HOME SEARCH BAR -->
  </div>
</template>

<script setup>
const city = ref('');
const cityError = ref(false);
const router = useRouter();

const handleSearch = () => {
  // router.push(`/city/${city.value}/car`); // 이거 대신 navigateTo로
  if (!city.value) {
    return (cityError.value = true);
  }
  navigateTo(`/city/${city.value}/car`);
};
</script>

<style lang="scss" scoped></style>
