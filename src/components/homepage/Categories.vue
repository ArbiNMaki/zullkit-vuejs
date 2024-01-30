<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";
import CategoriesCard from "../CategoriesCard.vue";

const categories = ref([]);

async function getCategoriesData() {
  try {
    const category = await axios.get(
      import.meta.env.VITE_API_URL + "/api/categories"
    );
    console.log(category.data);
    categories.value = category.data.data.data
  } catch (error) {
    console.error(error);
  }
}

onMounted(() => {
  getCategoriesData();
});
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12" id="categories">
    <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">Top Categories</h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <CategoriesCard
        v-for="category in categories"
        :key="category.id"
        :name="category.name"
        :products_count="category.products_count"
        :thumbnails="category.thumbnails"
      />

      <!-- <CategoriesCard title="Mobile UI Kit" :count="731" image="categories-1.jpg" /> -->
    </div>
  </div>
</template>

<style></style>
