<template>
  <div>
    <header class="shadow-sm bg-white">
      <nav class="container mx-auto p-4 flex justify-between">
        <NuxtLink to="/" class="font-bold">Nuxt Shop</NuxtLink>
        <ul class="flex gap-4">
          <!-- If we use normal anchor tag instead of Nuxtlink then browser make
          fresh new request to server and then server pre-render the page and sent back to browser.So for SPA ie Single Page Application we use NuxtLink -->
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/about">About</NuxtLink></li>
          <li><NuxtLink to="/products" class="btn">Products</NuxtLink></li>
          <li><NuxtLink to="/products/abc">abcProducts</NuxtLink></li>
        </ul>
      </nav>
    </header>

    <!-- output page content -->
    <div class="container mx-auto p-4">
      <!-- slot is a built in components nuxt gives which indicates that page content goes here -->
      <slot />
    </div>
  </div>
</template>
<style scoped>
.router-link-exact-active {
  color: #12b488;
}
</style>
