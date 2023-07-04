<template>
  <div class="bg-gray-900">
    <div
      class="px-4 py-5 mx-auto sm:max-w-xl md:max-w-full lg:max-w-screen-xl md:px-24 lg:px-8"
    >
      <div class="relative flex items-center justify-between">
        <a
          href="/"
          aria-label="Louth.beer"
          title="Louth.beer"
          class="inline-flex items-center"
        >
       <Logo />
          <span
            class="ml-2 text-xl font-bold tracking-wide text-amber-400 uppercase"
            >Louth.beer</span
          >
        </a>

        <ul class="flex items-center space-x-8">
          <li>
            <a
              href="/"
              class="inline-flex items-center justify-center h-12 px-6 font-medium tracking-wide text-black transition duration-200 rounded shadow-md bg-amber-400 hover:bg-amber-400 focus:shadow-outline focus:outline-none"
              aria-label="Find Beer"
              title="Find Beer"
            >
              Find Beer
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>

export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
};
</script>
