<script setup lang="ts">
const { data } = await useFetch(
  "https://fullstack-food-order.onrender.com/menu/all"
);
onMounted(() => {
  console.log(
    data?.value.map((value) => {
      return value.Picture;
    })
  );
});
</script>

<template>
  <div>this is the home</div>
  <div v-for="(data, index) in data">
    <NuxtImg :src="data.Picture[0]" width="100" height="100" alt="menu item" />
  </div>
</template>
