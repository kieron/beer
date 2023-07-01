<template>
  <div>
    <p>Title: {{ data.title }}</p>
    <p>Address: {{ data.address }}</p>
    <p>hasParking: {{ data.hasParking }}</p>
    <p>hasOutdoorSeating: {{ data.hasOutdoorSeating }}</p>
  </div>
</template>

<script setup>
const route = useRoute();

const { data } = useAsyncData(`content-${route.path}`, () =>
  queryContent().where({ _path: route.path }).findOne()
);
</script>

<style>
</style>