<template>
  <div class="contact uk-position-bottom-right uk-position-fixed uk-margin-bottom uk-margin-right">
    <div uk-lightbox>
      <a href="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4740.819266853735!2d9.99008871708242!3d53.550454675412404!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x3f9d24afe84a0263!2sRathaus!5e0!3m2!1sde!2sde!4v1499675200938" data-caption="Google Maps" data-type="iframe">
        <img class="mail" src="~/assets/img/icons/envelop.svg" alt="envelop" width="16" height="16" uk-svg>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$nextTick(this.moveEle);
  },

  methods: {
    moveEle() {
      const tm = this.$gsap.TweenLite;
      const img = document.querySelector('img.mail');

      tm.from(img, 1, { x: 50, ease: this.$gsap.Power1.easeOut })
    }
  }
}
</script>

<style scoped>
.contact {
  z-index: 10;
}
</style>

