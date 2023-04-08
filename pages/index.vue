<template>
  <!-- <Tutorial /> -->
  <div>
    <landingBG />
  </div>
</template>

<script>
import landingBG from '@/components/landingBG.vue'
export default {
  name: 'IndexPage',
  layout: 'NavbarFooterLayout',
  components: {
    landingBG,
  },
}
</script>
