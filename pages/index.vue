<template>
  <!-- <Tutorial /> -->
  <div>
    <landing />
    <Problem />
    <Solution />
    <MainPoint />
  </div>
</template>

<script>
import landing from '@/components/Landing.vue'
import Problem from '@/components/Problem.vue'
import Solution from '@/components/Solution.vue'
import MainPoint from '@/components/MainPoint.vue'
export default {
  name: 'IndexPage',
  layout: 'NavbarFooterLayout',
  components: {
    landing,
    Problem,
    Solution,
    MainPoint,
  },
}
</script>
