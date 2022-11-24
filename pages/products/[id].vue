<!-- If we want to show different products with changeable id on same page we use (param ) routes for same page so we created [id].vue file.Here id represents changeable part of products ie. route parameter. it creates routes like /products/:id. [] this brackets shows this part of file are changeable. -->
<!-- we show this changeable id in same components using use route composable function. -->
<template>
  <div>
    <!-- This is also one way of adding meta data using head tag  -->
    <Head>
      <Title>Nuxt Project |{{ product.title }}</Title>
      <Meta name="description" :content="product.description" />
    </Head>
    <!-- <p>Products Details for {{ id }}</p> -->
    <!-- <p>{{ product.title }}</p>
    <p>{{ product.price }}</p>
    <p>{{ product.id }}</p> -->
    <ProductDetails :product="product" />
  </div>
</template>
<script setup>
// the name inside {} must match to the file name.
const { id } = useRoute().params;

//to fetch products detail id
const uri = "https://fakestoreapi.com/products/" + id;
//fetches product second parameter is given that it should refetch new product
const { data: product } = await useFetch(uri, { key: id });

//third parameter in createError function is indicate that show error page if some of the link does not exits like abc product does not exits.When it set to true it forces application to show error page.
if (!product.value) {
  throw createError({
    statusCode: 404,
    statusMessage: "Product Not Found",
    fatal: true,
  });
}

//this method is used to link custom layouts.
definePageMeta({
  layout: "products-custom",
});
</script>
