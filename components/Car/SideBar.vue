<template>
  <div>
    <!-- CAR SIDE BAR -->
    <div class="shadow border w-64 mr-10 z-30 h-[190px]">
      <div class="p-5 flex justify-between relative cursor-pointer border-b">
        <h3>Location</h3>
        <h3 class="text-blue-400 capitalize" @click="updateModal('location')">
          {{ route.params.city }}
        </h3>
        <div
          v-if="modal.location"
          class="absolute border shadow left-56 p-5 top-1 -m-1 bg-white"
        >
          <input v-model="city" type="text" class="border p-1 rounded" />
          <button
            class="bg-blue-400 w-full mt-2 rounded text-white p-1"
            @click="onChangeLocation"
          >
            Apply
          </button>
        </div>
      </div>

      <div class="p-5 flex justify-between relative cursor-pointer border-b">
        <h3>Make</h3>
        <h3 class="text-blue-400 capitalize">Kia</h3>
      </div>
      <div class="p-5 flex justify-between relative cursor-pointer border-b">
        <h3>Price</h3>
        <h3 class="text-blue-400 capitalize">Any</h3>
      </div>
    </div>
    <!-- CAR SIDE BAR -->
  </div>
</template>

<script setup>
const modal = ref({
  make: false,
  location: false,
  price: false,
});

const updateModal = (key) => {
  modal.value[key] = !modal.value[key];
};

const city = ref('');
const route = useRoute();

const onChangeLocation = () => {
  if (!city.value) return;
  if (!isNaN(parseInt(city.value))) {
    throw createError({
      statusCode: 400,
      message: 'Invalid city format',
    });
  }
  updateModal('location');
  navigateTo(`/city/${city.value}/car/${route.params.make}`);
};
</script>

<style lang="scss" scoped></style>
