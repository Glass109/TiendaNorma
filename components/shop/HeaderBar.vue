<script setup lang="ts">
import Logo from "~/components/shop/Logo.vue";
import SearchBar from "~/components/shop/SearchBar.vue";

defineExpose({ changeValues });
const values = reactive({
  text: "",
  color: "text-black"
});
function changeValues(text: string = '', color: string = "text-black") {
  values.text = text;
  values.color = color;
}
</script>

<template>
  <header>
    <div class="border-b shadow w-full p-4 grid grid-cols-3 justify-items-center">
      <div id="logo">
        <nuxt-link to="/">
          <Transition name="fade" mode="out-in">
            <Logo v-if="!values.text"/>
            <h1 class="text-4xl font-extrabold" :class="[values.color]" v-else>{{ values.text }}</h1>
          </Transition>
        </nuxt-link>
      </div>
      <SearchBar/>
      <div id="extras" class="flex gap-4 items-center">
        <nuxt-link @mouseenter="changeValues('Carrito', 'text-yellow-500')" @mouseleave="changeValues()" to="/carrito" class="group flex flex-col items-center hover:text-yellow-500">
          <Icon size="2em" name="lucide:shopping-bag"/>
        </nuxt-link>
        <nuxt-link @mouseenter="changeValues('Favoritos', 'text-red-500')" @mouseleave="changeValues()" to="/favoritos" class="group flex flex-col items-center hover:text-red-500">
          <Icon size="2em" name="lucide:heart"/>
        </nuxt-link>
      </div>
    </div>
  </header>
</template>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>