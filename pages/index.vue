<script setup>
const { data: pubs } = await useAsyncData('pubs', () => {
  return queryContent().find()
})
</script>

<template>
  <div>
    <Hero/>
    <div class="container mx-auto p-5 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 space-6">
      <Card v-for="pub in pubs" :key="pub._path" :pub="pub" />
    </div>
  </div>
</template>