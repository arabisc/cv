<template>
  <div class="social uk-position-bottom-left uk-position-fixed uk-margin-small-left uk-margin-medium-bottom">
    <ul class="uk-iconnav uk-iconnav-vertical">
      <li><a class="social-icon" href="#" uk-icon="icon: instagram; ratio: 0.75;"></a></li>
      <li><a class="social-icon" href="#" uk-icon="icon: pinterest; ratio: 0.75;"></a></li>
      <li><a class="social-icon" href="#" uk-icon="icon: facebook; ratio: 0.75;"></a></li>
      <li><a class="social-icon" href="#" uk-icon="icon: twitter; ratio: 0.75;"></a></li>
    </ul>
  </div>
  <!-- Top Nav -->
</template>

<script>
export default {
  mounted() {
    this.$nextTick(this.moveEle);
  },

  methods: {
    moveEle() {
      const tl = new this.$gsap.TimelineMax();
      const elem = document.querySelectorAll('.social-icon');

      tl.staggerFrom(elem, 0.8, { x: -50, yoyo: true, ease: this.$gsap.Back.easeOut }, 0.4);
    }
  }
}
</script>

<style scoped>
  .social {
     z-index: 10;
  }
  .social-icon {
    color: #816f19;
  }
</style>