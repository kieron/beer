<script>
import { defineComponent } from "@vue/composition-api";

export default defineComponent({
  async setup(){
  },

});
</script>
<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
    <Card />
    <Card />
    <Card />
    <Card />
  </div>
</template>