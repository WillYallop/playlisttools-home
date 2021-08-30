<template>  
  <main>

    <div class="tempBanner">
      <div class="tempBannerInner">
        <div class="wrapper">

          <div class="tempBannerContent">
            <h1>Playlist Cover Maker</h1>
          </div>

        </div>
      </div>
    </div>


    <section class="sectionCon">
      <a href="https://cover-maker.playlisttools.io/" class="tempBtn">Visit Cover Maker App</a>
    </section>

  </main>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  layout: 'main',

})
</script>

<style lang="scss" scoped>
.tempBanner {
  width: 100%;
  padding: 1rem 1rem 0;
  position: relative;
  .tempBannerInner{
    background-color: #160F22;
    width: 100%;
    height: 100%;
    border-radius: 2rem;
    z-index: 10;
    position: relative;
    .wrapper {
      @include wrapper;
      padding-top: 9rem;
      height: 100%;
      .tempBannerContent {
        widows: 100%;
        padding: 6rem 0;
        h1 {
          color: #fff;
          font-size: 3rem;
        }
      }
    }
  }
}
.tempBtn {
  width: 100%;
  padding: 2rem;
  display: block;
  background-color: $accent1;
  border-radius: 2rem;
  color: #fff;
  font-size: 1.8rem;
  text-align: center;
}
</style>
