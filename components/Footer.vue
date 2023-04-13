<template>
  <footer class="shadow bg-gray-800">
    <div
      class="w-full mx-auto max-w-screen-xl p-4 md:flex md:items-center md:justify-center"
    >
      <span class="text-sm sm:text-center text-gray-400"
        >© {{ dateObject }}
        <a href="https://flowbite.com/" class="hover:underline">OLDIES™</a>. All
        Rights Reserved.
      </span>
    </div>
  </footer>
</template>

<script>
export default {
  setup() {
    const dateobj = new Date()

    // Year from the above object
    // is being fetched using getFullYear()
    let dateObject = dateobj.getFullYear()

    return { dateObject }
  },
}
</script>
