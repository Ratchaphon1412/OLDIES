<template>
  <!-- <Tutorial /> -->
  <div>
    <landing />
    <Problem />
    <Solution />
    <MainPoint />
    <TargetCustomer />
    <Endlanding />
  </div>
</template>

<script>
import landing from '@/components/Landing.vue'
import Problem from '@/components/Problem.vue'
import Solution from '@/components/Solution.vue'
import MainPoint from '@/components/MainPoint.vue'
import TargetCustomer from '@/components/TargetCustomer.vue'
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
    Endlanding,
  },
}
</script>
