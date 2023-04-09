<template>
  <section class="overflow-hidden">
    <div class="relative overflow-hidden background-city h-screen">
      <div
        class="absolute top-0 right-0 bottom-0 left-0 w-full h-full overflow-hidden bg-fixed"
        style="background-color: rgba(0, 0, 0, 0.25)"
      >
        <div class="flex justify-center items-center h-full">
          <div
            class="text-center text-white px-8 md:px-12 lg:w-1/2 md:w-2/3 sm:w-2/3 xs:w-2/3"
          >
            <h1
              class="xl:text-4xl lg:text-2xl md:text-xl xs:text-base ms:text-lg font-bold tracking-tight mb-12"
            >
              OLDIES
              <!-- OLDIES <br /><span>for your business</span> -->
            </h1>
            <p
              class="xl:text-xl md:text-base sm:text-sm xs:text-xs font-medium tracking-tight mb-12"
            >
              We connect health conscious travelers to top-notch medical,
              healthcare, and wellness facilities in Thailand. We are passionate
              about making high-quality healthcare services accessible and
              affordable for everyone.
            </p>
            <a
              class="inline-block px-7 py-3 mr-1.5 border-2 border-white text-white font-medium text-sm leading-snug uppercase rounded-full shadow-md hover:bg-black hover:bg-opacity-5 focus:outline-none focus:ring-0 transition duration-150 ease-in-out"
              data-mdb-ripple="true"
              data-mdb-ripple-color="light"
              href="#!"
              role="button"
              >Contact</a
            >
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.background-city {
  background-image: url('@/assets/images/sea_mounten.jpg');
  background-position: 50%;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
