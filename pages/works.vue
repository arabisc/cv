<template>
  <section class="container uk-padding">

    <h3 class="secondary-color uk-text-center head">list of my works</h3>

    <div class="projects uk-grid-match uk-child-width-1-3@s" uk-grid>
      <div class="project" v-for="(project, index) in projects" :key="project.title" :class="`project-${index}`">
        <i class="title uk-text-strong uk-display-block" :class="`title-${index}`">
          <b>{{ project.title }}</b>
        </i>
        <p class="para" :class="`para-${index}`">{{ project.para }}</p>
        <div class="uk-child-width-1-2" uk-grid>
          <div>
            <div uk-lightbox>
              <a href="/img/point-right.svg" uk-svg>
                <img src="~/assets/img/icons/camera.svg" alt="" uk-svg>
              </a>
              <a
              v-for="img in project.lightboxEle.imgs"
              :key="img.dataCaption"
              :href="img.src"
              :data-caption="img.dataCaption"
              >
              </a>
            </div>
          </div>
          <cite>
            <a :href="`${project.link}`" class="link readmore uk-display-block uk-text-primary" :class="`link-${index}`">
              <i>visit project</i>
              <span uk-icon="icon: arrow-right;"></span>
            </a>
          </cite>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {

  data() {
    return {
      projects: [
        {
          title: 'school managemet system',
          para: 'multi users lavel, adminstrators user, teachers user, students user ..ect, realtime inside chat, and more...',
          link: 'http://eedica.net',
          lightboxEle: {
            imgs: [
              { dataCaption: 'Landing Page', src: '/img/eedica_front.png' },
              { dataCaption: 'inside dashboard', src: '/img/eedica_users.png' },
              { dataCaption: 'sign up page', src: '/img/eedica_signUp.png' },
            ]
          }
        },
        {
          title: 'e-commerec platform',
          para: ' complate open shop cart and treading online website...',
          link: 'https://eshope-static.herokuapp.com/index.html',
          lightboxEle: {
            imgs: [
              { dataCaption: 'checkout page', src: '/img/ecommerec_chekout.png' },
              { dataCaption: 'cart page', src: '/img/ecommerec_cart.png' },
            ]
          }
        },
        {
          title: 'personal website',
          para: 'lite personal website and portfolio ... CMS, use graphicql no database system, so fast websit',
          link: '#',
          lightboxEle: {
            imgs: [
              { dataCaption: 'front page', src: '/img/personal_site_front.png' },
              { dataCaption: 'side navbar', src: '/img/personal_site_nav.png' },
            ]
          }
        },
        {
          title: 'Al-menbar magazin',
          para: 'arabic magazin web...build with core php, html, css, no library or framwork ....',
          link: 'http://alminbar.000webhostapp.com/',
          lightboxEle: {
            imgs: [
              { dataCaption: 'front page', src: '/img/al-menbar_fron.png' },
              { dataCaption: 'side navbar', src: '/img/al-menbar_fron2.png' },
            ]
          }
        },
        // {
        //   title: 'school managemet system',
        //   para: ' Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quae quis cupiditate, fugit ullam vitae quas?',
        //   link: 'view more details',
        // },
        // {
        //   title: 'school managemet system',
        //   para: ' Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quae quis cupiditate, fugit ullam vitae quas?',
        //   link: 'view more details',
        // },
        // {
        //   title: 'school managemet system',
        //   para: ' Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quae quis cupiditate, fugit ullam vitae quas?',
        //   link: 'view more details',
        // }
      ]
    }
  },
  mounted() {
    this.gsanime();
  },

  methods: {
    gsanime() {
      // Create a new Timeline (equivalent to new TimelineMax())
      const tl = this.$gsap.TweenMax;
      // Element To Animate
      const $ = document.querySelector.bind(document);

      const head = $('.head');
      const projects = document.querySelectorAll('.project');
      const eleAnime = [head, projects]

      tl.from(head, 0.3, { autoAlpha: 0, ease: this.$gsap.Linear.easeNone });
      tl.staggerFrom(projects, 0.5, { autoAlpha: 0 ,delay: .3,  ease: this.$gsap.Linear.easeNone }, 0.5);
    }
  }

}
</script>

<style scoped>
  i.title {
    font-size: 14px;
  }
  p {
    margin: 10px 0;
  }
  .readmore {
    font-size: 10px;
    font-weight: bold;
    color: var(--main-color);
    text-transform: uppercase;
  }
  h3 {
    text-shadow: 0.5px 0.5px 0px #454545;
  }
  @media screen and (max-width: 640px) {
    h3 {
      margin-top: 5vh;
    }
    cite a i {
      font-size: 8px;
    }
  }
</style>
