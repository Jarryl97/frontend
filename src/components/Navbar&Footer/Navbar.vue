<script setup lang="ts">
import { computed } from 'vue'

  const router = useRouter()
  const user = useUserStore()
  const isLoggedIn = computed(() => user.isLoggedIn)





  const logout = () => {
    user.logout()
    localStorage.clear();
    router.push('/')
  }


</script>

<template>


<nav class="bg-gray-100 border-gray-200 px-2 sm:px-4 py-2.5 rounded ">
  <div class="container flex flex-wrap items-center justify-between mx-auto">
    <KeepSake />
  <div class="flex md:order-2">
    <router-link v-if="!user.isLoggedIn.value" to="/auth/login" active-class="text-blue-600 underline" exact-active-class="text-blue-600 underline" class="ml-4 block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0 ">
      Login
    </router-link>
    <div v-else class="flex items-center md:order-2">
      <router-link to="/account/account">
          <button type="button" class="flex mr-3 text-sm bg-gray-800 rounded-full md:mr-0 focus:ring-4 focus:ring-gray-300" id="user-menu-button" aria-expanded="false" data-dropdown-toggle="user-dropdown" data-dropdown-placement="bottom">
            <img class="w-8 h-8 rounded-full" :src="user.currentUser?.profilePicUrl || 'https://www.gravatar.com/avatar/00000000000000000000000000000000?d=mp&f=y'" alt="user photo">
          </button>
        </router-link>
        <a @click="logout" class="ml-4 block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0">Sign Out</a>
    </div>
      <button data-collapse-toggle="mobile-menu-2" type="button" class="inline-flex items-center p-2 ml-1 text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="mobile-menu-2" aria-expanded="false">
        <span class="sr-only">Open main menu</span>
        <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
    </button>
  </div>
  <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1" id="navbar-sticky">
    <ul class="flex flex-col p-4 mt-4 border border-gray-100 rounded-lg md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:border-0">
      <li v-if="!isLoggedIn.value">
        <router-link to="/" active-class="text-blue-600 underline" exact-active-class="text-blue-600 underline" class="ml-4 block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0">Home</router-link>
      </li>
      <li v-if="isLoggedIn.value">
        <router-link to="/family" active-class="text-blue-600 underline" exact-active-class="text-blue-600 underline" class="block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0">Family</router-link>
      </li>
      <li v-if="isLoggedIn.value">
        <router-link to="/feed" active-class="text-blue-600 underline" exact-active-class="text-blue-600 underline" class="block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0">Feed</router-link>
      </li>
      <li v-if="!isLoggedIn.value">
        <router-link to="/auth/signup" active-class="text-blue-600 underline" exact-active-class="text-blue-600 underline" class="block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0">Sign Up</router-link>
      </li>
      <li v-if="isLoggedIn.value">
        <router-link to="/account/account" active-class="text-blue-600 underline" exact-active-class="text-blue-600 underline" class="block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0 ">Account</router-link>
      </li>
    </ul>
  </div>
  </div>
</nav>


</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;
}


</style>




