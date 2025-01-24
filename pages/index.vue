<script setup lang="ts">

import HeaderBar from "~/components/shop/HeaderBar.vue";
import Categories from "~/components/shop/Categories.vue";
import ShopBreadcrumb from "~/components/shop/ShopBreadcrumb.vue";
import Banner from "~/components/shop/Banner.vue";
</script>

<template>
  <HeaderBar/>
  <!-- TODO: Banner  -->
  <Banner/>
  <div class="container mx-auto my-4">
    <Categories class="mb-4"/>
    <ShopBreadcrumb/>
  </div>
</template>

<style scoped>

</style>