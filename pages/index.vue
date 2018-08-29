<template>
  <div class="main-container uk-flex uk-flex-center uk-text-center">
    <div class="content">
      <h1 class="heading uk-heading-primary">I am ahmad kassem <span class="secondary-color">koulaib</span></h1>
      <p class="sub-heading">
        After more than five years of study and learning, now i can introduce myself as a developer,
        <br> 
        designer and professional programmer ... happy to build your applications and websites..
      </p>
      <div class="uk-container uk-padding uk-width-3-4@s">
        <div class="tow-panels uk-child-width-1-2@s uk-grid-match" uk-grid>
          <div>
            <blockquote cite="#" class="uk-column-span uk-text-small">
              <p>
                Web Design Consultancy, <strong> WEB DEVELOPER</strong> June 2014 – Present
              </p>
              <footer class="uk-text-muted">
                Responsible for working closely with the product management
               </footer>
              <footer class="uk-text-muted">
                team to organise the web presence of clients, and to develop rich
                user interfaces for them
              </footer>
            </blockquote>
          </div>
          <div>
            <blockquote cite="#" class="uk-column-span uk-text-small">
              <p>Mastery of more than 17 languages software and library software and framework</p>
              <footer class="uk-text-small uk-text-muted">
                i am interested in and follow every new in the world of technology, programming and design ...
                <cite><nuxt-link to="skills">visit the skills part</nuxt-link></cite></footer>
            </blockquote>
          </div>
        </div>
      </div>
      <div class="uk-flex uk-flex-center uk-margin">
        <ul class="uk-subnav" uk-margin>
          <li>
            <a href="#" class="cv-download sequare-border uk-button uk-button-default uk-box-shadow-small">
              <span uk-icon="icon: cloud-download"></span>
              download CV
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'page-index',

    mounted() {
      this.$nextTick(this.movePageEle);
    },

    methods: {
      movePageEle() {
        const $ = document.querySelector.bind(document);
        // Create New Time Greensock LineTime
        const tl = new this.$gsap.TimelineMax();
        // Element To Anime
        const heading = $('.heading');
        const subHeading = $('.sub-heading');
        const towPanels = document.querySelectorAll('.tow-panels div');
        const cvDownload = $('.cv-download')

        const eleAnime = [heading, subHeading, towPanels, cvDownload];

        // Start Animation
        tl.staggerFrom(eleAnime, 0.8, { autoAlpha: 0, y: '+=80', ease: this.$gsap.Back.easeOut }, 0.3);
      }
    }
  }
</script>

<style scoped>
  .content {
    margin-top: 10vh;
  }
  .content h1 {
    color: #aaaaaa;
    text-shadow: 1px 0px 0px #454545;
  }
</style>