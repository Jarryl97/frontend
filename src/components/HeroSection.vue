<!-- This example requires Tailwind CSS v3.0+ -->
<script setup>
import { ref } from 'vue'
import { Dialog, DialogPanel } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'

const navigation = [
  { name: 'Product', href: '#' },
  { name: 'Features', href: '#' },
  { name: 'Marketplace', href: '#' },
  { name: 'Company', href: '#' },
]
const { t } = useI18n()

const mobileMenuOpen = ref(false)
</script>

<template>
  <section class="mb-40">

    <svg
      data-name="Layer 1"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1440 320"
      preserveAspectRatio="none"
      class="svg absolute hidden lg:block"
      style="height: 560px; width: 100%; z-index: -10; overflow: hidden"
    >
      <defs>
        <linearGradient id="sw-gradient-0" x1="0" x2="0" y1="1" y2="0">
          <stop stop-color="hsl(217, 102%, 99%)" offset="0%"></stop>
          <stop stop-color="hsl(217,88%, 93%)" offset="100%"></stop>
        </linearGradient>
      </defs>
      <path
        fill="url(#sw-gradient-0)"
        d="M 0.351 264.418 C 0.351 264.418 33.396 268.165 47.112 270.128 C 265.033 301.319 477.487 325.608 614.827 237.124 C 713.575 173.504 692.613 144.116 805.776 87.876 C 942.649 19.853 1317.845 20.149 1440.003 23.965 C 1466.069 24.779 1440.135 24.024 1440.135 24.024 L 1440 0 L 1360 0 C 1280 0 1120 0 960 0 C 800 0 640 0 480 0 C 320 0 160 0 80 0 L 0 0 L 0.351 264.418 Z"
      ></path>
    </svg>

    <div class="px-6 py-12 lg:my-12 md:px-12 text-gray-800 text-center lg:text-left">
      <div class="container mx-auto xl:px-32">
        <div class="grid lg:grid-cols-2 gap-12 flex items-center">
          <div class="mt-12 lg:mt-0">
            <h1 class="text-5xl md:text-6xl xl:text-7xl font-bold tracking-tight mb-12">Keepsake <br /><span class="text-blue-600">Share your Stories and Memories</span></h1>
            <a class="bg-gradient-to-r from-blue-600 to-blue-800 rounded-md hover:from-blue-800  hover:to-blue-900 text-white font-bold py-2 px-4 rounded shadow-lg" data-mdb-ripple="true" data-mdb-ripple-color="light" href="/auth/signup" role="button">Get started</a>
            <a class="inline-block px-7 py-3 bg-transparent text-blue-600 font-medium text-sm leading-snug uppercase rounded hover:text-blue-700 hover:bg-gray-100 focus:bg-gray-100 focus:outline-none focus:ring-0 active:bg-gray-200 transition duration-150 ease-in-out" data-mdb-ripple="true" data-mdb-ripple-color="light" href="/auth/login" role="button">Log in</a>
          </div>
          <div class="mb-12 lg:mb-0">
            <img
              src="https://imgs.search.brave.com/idfB1ukUODyBZOaaA0PzHfZ1oQfTLx7gxHnPmG3R24M/rs:fit:1200:1200:1/g:ce/aHR0cHM6Ly9hZHZh/bnRhZ2U0cGFyZW50/cy5jb20vd3AtY29u/dGVudC91cGxvYWRz/LzIwMTcvMTEvaGFw/cHktZmFtaWx5Lmpw/Zw"
              class="w-full rounded-lg shadow-lg"
              alt=""
              style="opacity: 0.7;"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
