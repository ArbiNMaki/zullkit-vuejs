<script setup>
import { ref } from "vue";
import NewItemsCard from "../NewItemsCard.vue";

const items = ref([
  {
    id: 1,
    title: "Mobile UI Kit",
    categories: "Mobile UI Kit",
    image: "items-1.jpg",
  },
  {
    id: 2,
    title: "Online Doctor Consultation",
    categories: "Website UI Kit",
    image: "items-2.jpg",
  },
  {
    id: 3,
    title: "Banking Crypto",
    categories: "Mobile UI Kit",
    image: "items-3.jpg",
  },
]);
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
    <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">New Items</h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <NewItemsCard
        v-for="item in items"
        :key="item.id"
        :title="item.title"
        :categories="item.categories"
        :image="item.image"
        :id="item.id"
      />
    </div>
  </div>
</template>

<style></style>
