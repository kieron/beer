<template>
  <div class="min-h-screen bg-amber-100">
    <main class="profile-page">
      <section class="relative block h-52 md:h-96">
        <div
          class="absolute top-0 w-full h-full bg-center bg-cover"
          :style="{ backgroundImage: `url(${data.image})` }"
        >
          <span
            id="blackOverlay"
            class="w-full h-full absolute opacity-50 bg-black"
          ></span>
        </div>
      </section>
      <section class="relative py-16">
        <div class="container mx-auto px-4">
          <div
            class="relative flex flex-col min-w-0 break-words bg-white w-full mb-6 shadow-xl rounded-lg -mt-32"
          >
            <div class="px-6">
              <div class="flex flex-wrap justify-center">
                <div class="w-full lg:w-4/12 px-4 lg:order-1">
                  <div class="flex justify-center py-4 lg:pt-4 pt-8">
                    <div class="mr-4 p-3 text-center">
                      <span
                        class="text-xl font-bold block uppercase tracking-wide text-gray-700"
                        v-if="data.hasParking"
                      >
                        <i class="fas fa-parking text-amber-500"></i>
                      </span>
                      <span class="text-sm text-gray-500">Parking</span>
                    </div>
                    <div class="mr-4 p-3 text-center">
                      <span
                        class="text-xl font-bold block uppercase tracking-wide text-gray-700"
                        v-if="data.hasOutdoorSeating"
                      >
                        <i class="fas fa-umbrella-beach text-amber-500"></i>
                      </span>
                      <span class="text-sm text-gray-500">Garden</span>
                    </div>
                    <div class="lg:mr-4 p-3 text-center">
                      <span
                        class="text-xl font-bold block uppercase tracking-wide text-gray-700"
                        v-if="data.dogFriendly"
                      >
                        <i class="fas fa-dog text-amber-500"></i>
                      </span>
                      <span class="text-sm text-gray-500">Dog Friendly</span>
                    </div>
                  </div>
                </div>
              </div>
              <div class="text-center mt-12">
                <h3
                  class="text-4xl font-semibold leading-normal mb-2 text-gray-800 mb-2"
                >
                  {{ data.title }}
                </h3>
                <div
                  class="text-sm leading-normal mt-0 mb-2 text-gray-500 font-bold uppercase"
                >
                  <i
                    class="fas fa-map-marker-alt mr-2 text-lg text-gray-500"
                  ></i>
                  {{ data.address }}
                </div>
                <div class="mb-2 text-gray-700 mt-10" v-if="data.servesFood">
                  <i class="fas fa-utensils mr-2 text-lg text-gray-500"></i>
                  Serves Food
                </div>
                <div class="mb-2 text-gray-700" v-if="data.liveMusic">
                  <i class="fas fa-music mr-2 text-lg text-gray-500"></i>
                  Live Music
                </div>
                <div class="mb-2 text-gray-700" v-if="data.hasPoolTable">
                  <i class="fas fa-gamepad mr-2 text-lg text-gray-500"></i>
                  Pool Table
                </div>
              </div>
              <div class="mt-10 py-10 border-t border-gray-300 text-center">
                <div class="flex flex-wrap justify-center">
                  <div class="w-full lg:w-9/12 px-4">
                    <p class="mb-4 text-lg leading-relaxed text-gray-800">
                      {{ data.description }}
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
    <footer-component></footer-component>
  </div>
</template>

<script setup>
const route = useRoute();

const { data } = useAsyncData(`content-${route.path}`, () =>
  queryContent().where({ _path: route.path }).findOne()
);
</script>

<style>
.profile-page {
  background-color: rgb(254 243 199);
}
</style>