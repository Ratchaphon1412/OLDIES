<template>
  <!-- <Tutorial /> -->
  <div>
    <landing />
    <Problem />
  </div>
</template>

<script>
import landing from '@/components/Landing.vue'
import Problem from '@/components/Problem.vue'
export default {
  name: 'IndexPage',
  layout: 'NavbarFooterLayout',
  components: {
    landing,
    Problem,
  },
}
</script>
