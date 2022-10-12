<template>
  <nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-900">
    <div class="container flex flex-wrap justify-between items-center mx-auto">
      <div class="hidden w-full md:block md:w-auto">
        <a href="#" class="block w-32">
          <img src="/assets/img/logo.png" class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" style="height: 50px"/>
        </a>
      </div>
      <div class="hidden w-full md:block md:w-auto">
        <ul class="flex flex-col p-4 mt-4 bg-gray-50 rounded-lg md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 ">
          <li>
            <nuxt-link :to="{ name: 'admin-category' }">
              <a href="#" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
                Category
              </a>
            </nuxt-link>
          </li>
          <li>
            <nuxt-link :to="{ name: 'admin-tag' }">
              <a href="#" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
                Tag
              </a>
            </nuxt-link>
          </li>
          <li>
            <nuxt-link :to="{ name: 'admin-product' }">
              <a href="#" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
                Product
              </a>
            </nuxt-link>
          </li>
          <li>
            <nuxt-link :to="{ name: 'admin-order' }">
              <a href="#" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
                Oder
              </a>
            </nuxt-link>
          </li>
          <li>
            <a href="#" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent" @click="logout">
              Log out
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  methods: {
    logout() {
      this.$store.dispatch('logout')
      this.$router.push({ name: 'login' })
    }
  }
}
</script>
