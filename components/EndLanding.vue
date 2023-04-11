<template>
  <section class="overflow-hidden">
    <div class="relative overflow-hidden background-city h-screen">
      <div
        class="absolute top-0 right-0 bottom-0 left-0 w-full h-full overflow-hidden bg-fixed js-show-on-scroll"
        style="background-color: rgba(0, 0, 0, 0.3)"
      >
        <div class="flex justify-center items-center h-full">
          <div
            class="text-center text-white px-8 md:px-12 lg:w-1/2 md:w-2/3 sm:w-2/3 xs:w-2/3"
          >
            <h1
              class="xl:text-4xl lg:text-2xl md:text-xl xs:text-base ms:text-lg font-bold tracking-tight mb-12"
            >
              Coming soon
              <!-- OLDIES <br /><span>for your business</span> -->
            </h1>
            <p
              class="xl:text-xl md:text-base sm:text-sm xs:text-xs font-medium tracking-tight mb-12"
            >
              Get ready to transform your medical and wellness experience in
              Thailand with Oldies! Our innovative app is coming soon,
              connecting you with top-quality healthcare providers and
              personalized treatments at your fingertips. Discover, compare, and
              book top-quality facilities with ease, transparency, and
              confidence. Stay tuned for the launch and join us on this exciting
              journey to revolutionize your medical & wellness experience!
            </p>
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
