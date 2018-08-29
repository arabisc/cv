<template>
  <section class="uk-container uk-flex uk-flex-middle uk-flex-center uk-text-center">
    <div class="content">
      <div class="personal-img">
        <img src="/img/personal.png" width="150" height="150" alt="ahamd kassem koulaib" class="uk-border-circle">
        <p class="uk-article-meta uk-margin-small">Written on 12 April 2018</p>
      </div>

      <div class="uk-margin">
        <article class="uk-article">
          <h3 class="title secondary-color uk-text-center head">about me</h3>
          <p class="first">
            <i class="text uk-text-strong">
              I am Ahmad Klaib, I born in <b class="secondary-color">Talkalakh</b>  Town in 1984, <abbr title="text">I left Syria in 2012 to Lebanon</abbr> , I started learning coding there,
              <br>
              I fall in love coding and web languages especially, I am spending almost of the time in acquiring new software skills.
            </i>
          </p>
          <p class="last">
            <i class="text uk-text-strong">
              <q>I am hard worker</q>, I work 14 hours a day, I have built many web sites in different coding languages,<br>I have more than five years of experience in web design and programming,<br> I can work on almost web develop languages but I am  perfect in <span class="secondary-color">Java script, php, python</span>, and its liberaries
              <br>
              <b>Coding became my passion,</b> I follow a day by day to learn any new skill in programming   
            </i>
          </p>
          <div class="address uk-grid-small uk-margin-medium-bottom uk-margin-left" uk-grid>
            <div class="uk-width-1-2@s">
              <ul class="uk-subnav uk-text-center">
                <li>
                  <a href="#">
                    <img src="~/assets/img/icons/mail2.svg" alt="ahamd" width="12" height="12" uk-svg>
                    arabisc95@gmail.com
                  </a>
                </li>
                <li>
                  <a href="#">
                    <img src="~/assets/img/icons/chrome.svg" alt="ahamd" width="12" height="12" uk-svg>
                    https://arabisc.com
                  </a>
                </li>
              </ul>
            </div>
            <div class="uk-width-1-2@s">
              <ul class="uk-subnav ul-text-center">
                <li>
                  <a href="#">
                    <img src="~/assets/img/icons/point-right.svg" alt="ahamd" width="12" height="12" />
                    triboli-south-libnaon-moharam
                  </a>
                </li>
                <li>
                  <a href="#">
                    <img src="~/assets/img/icons/phone.svg" alt="ahamd" width="12" height="12" uk-svg>
                    00961-76-114-669
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </article>
      </div>
        
    </div>
  </section>
</template>

<script>
  export default {
    name: 'page-about',

    head () {
      return {
        
      }
    },
    mounted() {
      this.$nextTick(this.movePageEle)
    },

    methods: {
      movePageEle() {
        const $ = document.querySelector.bind(document);
        // Create New Time Greensock LineTime
        const tl = new this.$gsap.TimelineMax();
        // Element To Anime
        const img = $('.personal-img > img');
        const metaPar = $('.personal-img > p');
        const title = $('article > .title');
        const paraFirst = $('article .first');
        const paraLast = $('article .last');
        const address = $('.address');
        const eleAnime = [img, metaPar, title, paraFirst, paraLast, address]

        tl.staggerFrom(eleAnime, .8, { y: '+=80', autoAlpha: 0, ease: this.$gsap.Back.easeOut }, .3)

      }
    }
  }
</script>

<style scoped>
.content {
  margin-top: 2.5vh;
}
.uk-subnav > li > a {
  font-size: 9px;
  font-weight: normal;
}
h3 {
  text-shadow: 0.5px 0.5px 0px #454545;
}
@media screen and (max-width: 640px) {
  .content {
    margin-top: 10vh;
  }
  .personal-img img {
    width: 100px;
    height: 100px;
  }
  p.first > i, p.last > i {
    font-size: 11px;
  }
}
</style>
