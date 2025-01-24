<script setup lang="ts">
import Logo from "~/components/shop/Logo.vue";
import SearchBar from "~/components/shop/SearchBar.vue";

type LogoProps = {
  text?: string;
  color?: string;
}

const props = defineProps<LogoProps>();


</script>

<template>
  <header>
    <div class="border-b shadow w-full flex justify-around gap-4 p-4 items-center">
      <div id="logo">
        <nuxt-link to="/">
          <Logo v-if="!text"/>
          <h1 :class="[color]" v-else>{{ text }}</h1>
        </nuxt-link>
      </div>
      <SearchBar class="grow"/>
      <div id="extras" class="flex gap-4 items-center">
        <NuxtLink to="/carrito" class="group flex flex-col items-center hover:text-yellow-500">
          <Icon size="1.3em" name="lucide:shopping-cart"/>
          <p>Carrito</p>
        </NuxtLink>
        <NuxtLink to="/favoritos" class="group flex flex-col items-center hover:text-red-500">
          <Icon size="1.3em" name="lucide:heart" </Icon>
          <p>Favoritos</p>
        </NuxtLink>
      </div>
    </div>
  </header>
</template>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>