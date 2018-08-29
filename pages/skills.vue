<template>
  <section class="main-container">
    <div class="content">
      <!-- <div class="uk-container uk-padding uk-width-3-4@s">
        <h3 class="secondary-color uk-text-center head">list of my skills</h3>
        <ul class="uk-list uk-list-bullet uk-margin-medium-top uk-margin-large-left">
          <li v-for="bar in progressBars" :key="bar.class">
            <p class="uk-text-strong">
              {{ bar.class }}
              <span
              class="progress"
              :class="`progress-${bar.class}`"
              :style="{ width: bar.width }"
              >
              </span>
             <span class="counter" :class="`counter-${bar.class}`" v-text="`${bar.counter}%`" :style="{ left: `${bar.left}`}"></span>
            </p>
          </li>
        </ul>
      </div> -->
      <h3 class="secondary-color uk-text-center head">list of my skills</h3>
      <div class="list uk-margin">
        <ul class="uk-list uk-list-bullet uk-margin-medium-top">
          <li v-for="bar in progressBars" :key="bar.class">
            <p class="uk-text-strong">
              {{ bar.class }}
              <span
              class="progress"
              :class="`progress-${bar.class}`"
              :style="{ width: bar.width }"
              >
              </span>
             <span class="counter" :class="`counter-${bar.class}`" v-text="`${bar.counter}%`" :style="{ left: `${bar.left}`}"></span>
            </p>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'page-skills',

  data() {
    return {
      progressBars: [
        { class: 'ui-ux', width: '40%', left: '50%', counter: '80' },
        { class: 'html', width: '48%', left: '50%', counter: '95' },
        { class: 'css', width: '48%', left: '50%', counter: '95' },
        { class: 'javascript', width: '46%', left: '50%', counter: '93' },
        { class: 'php', width: '48%', left: '50%', counter: '95' },
        { class: 'node', width: '48%', left: '50%', counter: '95' },
        { class: 'ruby', width: '40%', left: '50%', counter: '80' },
        { class: 'bython', width: '42.5%', left: '50%', counter: '85' },
        { class: 'SQL', width: '48%', left: '50%', counter: '95' },
        { class: 'NoSQL', width: '45%', left: '50%', counter: '90' },
        { class: 'GraphQL', width: '45%', left: '50%', counter: '90' },
      ],
    };
  },

  mounted() {
    this.$nextTick(this.moveProgress);
  },

  methods: {
    moveProgress() {
      const $ = document.querySelector.bind(document);
      // Create a new Timeline (equivalent to new TimelineMax())
      const tl = this.$gsap.TweenMax;
      const progress = document.querySelectorAll('.progress');
      const counter = document.querySelectorAll('.counter');

      tl
      .staggerFrom(progress, .8, { width: 0, ease: this.$gsap.Back.easeOut }, .2);
      tl
      .staggerFrom(counter, .8, { autoAlpha: 0, ease: this.$gsap.Back.easeOut }, .2);
    }
  }
}
</script>

<style scoped>
  .list {
    margin-left: 20vw;
  }
  .uk-list li {
    margin: 15px 0;
  }
  .uk-list > li > p {
    margin-left: -15px;
  }
  .progress {
    position: absolute;
    top: 100%;
    left: 8px;
    height: 2px;
    background-color: aliceblue;
  }
  .counter {
    position: absolute;
    top: calc(100% - 12px);
    color: aliceblue;
    margin-left: 10px;
    color: #816f19;
  }
  h3 {
    text-shadow: 0.5px 0.5px 0px #454545;
  }
  @media screen and (max-width: 640px) {
    .content {
      margin: 10vh 0 10vh 0;
    }
    .list {
      margin-left: 5vw;
      width: 100%;
    }
    .uk-list > li > p {
     font-size: 11px;
    }
  }
</style>

