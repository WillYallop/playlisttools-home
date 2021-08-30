<template>
  <main>
    <HomeCardTrio/>
    <div class="bellowFold">
      <HomeCardSlider/>
      <HomeLatestStories/>
      <HomePricingTables/>
      <CtaDownload/>
    </div>
  </main>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  layout: 'main',

})
</script>


<style lang="scss" scoped>
.bellowFold {
  content-visibility: auto;
  contain-intrinsic-size: 0 1000px; 
}
</style>