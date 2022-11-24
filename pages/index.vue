<template>
  <div
    class="md:container md:mx-auto h-96 bg-green-100 max-w-full justify-between"
  >
    <h2 class="text-blue-800 text-3xl pt-10 mx-10 text-justify">Welcome</h2>
    <img
      class="float-right mx-5 rounded-full h-62 w-72"
      src="https://img.freepik.com/premium-vector/clothing-store-logo-design-inspiration-vector-illustration_500223-481.jpg"
    />
    <p class="mx-10 py-3 justify-start">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio nulla
      sequi dignissimos, veniam veritatis laboriosam est unde consequatur in
      illo. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Veritatis
      eos dolore quos debitis odit qui ipsam atque quisquam laboriosam soluta?
    </p>
    <NuxtLink to="/products">
      <button
        class="btn mx-8 mt-5 py-2 px-4 bg-teal-500 text-white font-semibold rounded-lg shadow-md hover:bg-teal-700 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75"
      >
        Shop Now
      </button>
    </NuxtLink>
  </div>
</template>
<style scoped>
/* h2 {
  margin-bottom: 20px;
  font-size: 36px;
} */
/* p {
  margin: 20px 0;
} */
</style>
