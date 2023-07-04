<script>
import { defineComponent } from "@vue/composition-api";

export default defineComponent({
  async setup() {},
});
</script>
<template>
<div class="">
  <Hero/>
  <div class="container mx-auto p-5 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 space-6">
    <Card />
    <Card />
    <Card />
    <Card />
  </div>
  </div>
</template>