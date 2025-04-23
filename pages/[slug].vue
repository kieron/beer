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
              <div class="text-center mt-12">
                <h3
                  class="text-4xl font-semibold leading-normal mb-2 text-gray-800"
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

                <div class="mt-8 py-10 border-t border-gray-300">
                  <div class="flex flex-wrap justify-center gap-4">
                    <div v-if="data.hasParking" class="feature-tag">
                      <svg class="h-5 w-5 fill-current text-gray-800" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
                        <path d="M570.53,242,512,190.75V48a16,16,0,0,0-16-16H400a16,16,0,0,0-16,16V78.75L298.53,4a16,16,0,0,0-21.06,0L5.47,242a16,16,0,0,0,21.07,24.09L64,233.27V464a48.05,48.05,0,0,0,48,48H464a48.05,48.05,0,0,0,48-48V233.27l37.46,32.79A16,16,0,0,0,570.53,242ZM480,464a16,16,0,0,1-16,16H112a16,16,0,0,1-16-16V205.27l192-168,192,168Zm0-301.25-64-56V64h64ZM208,218.67V325.34A26.75,26.75,0,0,0,234.66,352H341.3A26.76,26.76,0,0,0,368,325.34V218.67A26.75,26.75,0,0,0,341.3,192H234.66A26.74,26.74,0,0,0,208,218.67ZM240,224h96v96H240Z"></path>
                      </svg>
                      <span>Parking Available</span>
                    </div>
                    <div v-if="data.hasOutdoorSeating" class="feature-tag">
                      <svg class="h-5 w-5 fill-current text-gray-800" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                        <path d="M399.959 170.585c-4.686 4.686-4.686 12.284 0 16.971L451.887 239H60.113l51.928-51.444c4.686-4.686 4.686-12.284 0-16.971l-7.071-7.07c-4.686-4.686-12.284-4.686-16.97 0l-84.485 84c-4.686 4.686-4.686 12.284 0 16.971l84.485 84c4.686 4.686 12.284 4.686 16.97 0l7.071-7.07c4.686-4.686 4.686-12.284 0-16.971L60.113 273h391.773l-51.928 51.444c-4.686 4.686-4.686 12.284 0 16.971l7.071 7.07c4.686 4.686 12.284 4.686 16.97 0l84.485-84c4.687-4.686 4.687-12.284 0-16.971l-84.485-84c-4.686-4.686-12.284-4.686-16.97 0l-7.07 7.071z"></path>
                      </svg>
                      <span>Beer Garden</span>
                    </div>
                    <div v-if="data.dogFriendly" class="feature-tag">
                      <svg class="h-5 w-5 fill-current text-gray-800" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
                        <path d="M288 0C126.5 0 0 100.3 0 224c0 70.1 38.3 132.3 97.5 174.5-.9-4.5-1.5-9.1-1.5-13.8V288c0-17.7 14.3-32 32-32h32c17.7 0 32 14.3 32 32v32c0 17.7 14.3 32 32 32h32c17.7 0 32-14.3 32-32v-32c0-17.7 14.3-32 32-32h32c17.7 0 32 14.3 32 32v76.7c0 4.7-.6 9.3-1.5 13.8C537.7 356.3 576 294.1 576 224 576 100.3 449.5 0 288 0zM144 160c-8.8 0-16-7.2-16-16s7.2-16 16-16 16 7.2 16 16-7.2 16-16 16z"></path>
                      </svg>
                      <span>Dog Friendly</span>
                    </div>
                    <div v-if="data.servesFood" class="feature-tag">
                      <svg class="h-5 w-5 fill-current text-gray-800" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                        <path d="M416 32H96C42.98 32 0 74.98 0 128v256c0 53.02 42.98 96 96 96h320c53.02 0 96-42.98 96-96V128c0-53.02-42.98-96-96-96zM96 64h320c35.29 0 64 28.71 64 64v32H32v-32c0-35.29 28.71-64 64-64zm320 384H96c-35.29 0-64-28.71-64-64v-32h448v32c0 35.29-28.71 64-64 64z"></path>
                      </svg>
                      <span>Food Service</span>
                    </div>
                    <div v-if="data.liveMusic" class="feature-tag">
                      <svg class="h-5 w-5 fill-current text-gray-800" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
                        <path d="M532.01 386.17C559.48 359.05 576 325.04 576 288c0-80.02-76.45-146.13-176.18-157.94 0 .01.01.02.01.03C368.37 72.47 294.34 32 208 32 93.12 32 0 103.63 0 192c0 37.04 16.52 71.05 43.99 98.17-15.3 30.74-37.34 54.53-37.7 54.89-6.31 6.69-8.05 16.53-4.42 24.99A23.085 23.085 0 0 0 23.06 384c53.54 0 96.67-20.24 125.17-38.78 9.08 2.09 18.45 3.68 28 4.82C207.74 407.59 281.73 448 368 448c20.79 0 40.83-2.41 59.77-6.78C456.27 459.76 499.4 480 552.94 480c9.22 0 17.55-5.5 21.18-13.96 3.64-8.46 1.89-18.3-4.42-24.99-.35-.36-22.39-24.14-37.69-54.88z"></path>
                      </svg>
                      <span>Live Music</span>
                    </div>
                    <div v-if="data.hasPoolTable" class="feature-tag">
                      <svg class="h-5 w-5 fill-current text-gray-800" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                        <path d="M256 0C114.6 0 0 114.6 0 256s114.6 256 256 256 256-114.6 256-256S397.4 0 256 0zm0 448c-105.9 0-192-86.1-192-192S150.1 64 256 64s192 86.1 192 192-86.1 192-192 192z"></path>
                      </svg>
                      <span>Pool Table</span>
                    </div>
                  </div>
                </div>

                <div class="mt-10 py-10 border-t border-gray-300">
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

.feature-tag {
  @apply flex items-center gap-2 px-4 py-2 rounded-full bg-amber-100 text-amber-900 font-medium text-sm transition-all duration-300 hover:bg-amber-200;
}

.feature-tag svg {
  @apply mr-2;
}
</style>