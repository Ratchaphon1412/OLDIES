<template>
  <!-- <Tutorial /> -->
  <div class="font-Poppins">
    <landing />
    <Problem />
    <Solution />
    <MainPoint />
    <!-- <TargetCustomer /> -->
    <Contact />
    <Endlanding />
  </div>
</template>

<script>
import landing from '@/components/Landing.vue'
import Problem from '@/components/Problem.vue'
import Solution from '@/components/Solution.vue'
import MainPoint from '@/components/MainPoint.vue'
import TargetCustomer from '@/components/TargetCustomer.vue'
import Contact from '@/components/Contect.vue'
import Endlanding from '@/components/EndLanding.vue'
export default {
  name: 'IndexPage',
  layout: 'NavbarFooterLayout',
  components: {
    landing,
    Problem,
    Solution,
    MainPoint,
    TargetCustomer,
    Contact,
    Endlanding,
  },
  mounted() {
    const callback = function (entries) {
      entries.forEach((entry) => {
        console.log(entry)

        if (entry.isIntersecting) {
          entry.target.classList.add('animate-fadeIn')
        } else {
          entry.target.classList.remove('animate-fadeIn')
        }
      })
    }

    const observer = new IntersectionObserver(callback)

    const targets = document.querySelectorAll('.js-show-on-scroll')
    targets.forEach(function (target) {
      target.classList.add('opacity-0')
      observer.observe(target)
    })
  },
}
</script>
