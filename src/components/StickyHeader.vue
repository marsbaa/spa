<template>
<div>
<nav class="flex justify-between items-center flex-wrap bg-white p-6 fixed pin-t pin-l pin-r">
  <div class="flex items-center flex-no-shrink text-gold mr-6">
    <span class="font-semibold text-xl tracking-tight">loyalty</span>
    <span>Corp</span>
  </div>
  <div class="block lg:hidden">
    <button class="flex items-center px-3 py-2 border rounded text-grey-darker border-grey-light hover:text-blue hover:border-blue-light" @click="showMenu = !showMenu">
      <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
    </button>
  </div>
  <div class="w-full justify-end block lg:flex lg:items-center lg:w-auto" :class="showMenu ? 'block': 'hidden'">
    <div class="text-sm lg:flex-grow">
      <a v-for="(item, i) in menuItems" :key="i" :href="item.link" class="block mt-4 lg:inline-block lg:mt-0 text-grey-darker hover:text-blue mr-4 no-underline">
        {{item.label}}
      </a>
    </div>
  </div>
</nav>
</div>

</template>

<script>
  export default {
    data() {
      return {
        showMenu: false,
        menuItems: [
          { label : 'Home', link: '#'},
          { label: 'Who we are', link: '#'},
          { label: 'What we do', link: '#'}
        ]
      }
    }
  }
</script>
