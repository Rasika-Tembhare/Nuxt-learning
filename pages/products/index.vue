<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in products">
        <!-- here we have use props thats why we data bind(:to) to and we use template string as id is coming from api -->
        <!-- <NuxtLink :to="`/products/${p.id}`">{{ p.title }}</NuxtLink> -->
        <ProductCard :product="p" />
        <!-- here we use product prop and it is dynamic using: -->
      </div>
    </div>
  </div>
</template>

<script setup>
//this method is used to link custom layouts.
definePageMeta({
  layout: "products-custom",
});

//fetch products from api using builtin useFetch function and inside {} it comes in data but we use as products by using :
const { data: products } = await useFetch("https://fakestoreapi.com/products");

//another way of writing meta data using useHead method.
useHead({
  title: "Nuxt Project |Product",
  meta: [{ name: "description", content: "Product list" }],
});
</script>
