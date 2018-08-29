<template>
  <div class="default background-secondary uk-width-1-1">
    <div class="default-container uk-width-1-1 uk-position-absolute">
      <div class="default-bg background-secondary uk-width-1-1 uk-position-absolute">
      </div>
      <div class="mouse-icon-circle" id="mouse-icon-circle"
      :style="{ width: icon.width, height: icon.height }">
        <div>
          <span class="mouse-icon-square" id="mouse-icon-square"></span>
        </div>
      </div>
      <!-- Follow Mouse -->
      <div class="default-content uk-text-muted">
        <TopNav />
        <TopTitle />
        <Contact />
        <CopyRight />
        <Social />
        <div class="uk-container pages-content uk-z-index uk-position-relative">
          <nuxt/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const TopNav = () => import('~/components/TopNav.vue');
const TopTitle = () => import('~/components/TopTitle.vue');
const Social = () => import('~/components/Social.vue');
const CopyRight = () => import('~/components/CopyRight.vue');
const Contact = () => import('~/components/Contact.vue');

export default {
  name: 'default-page',
  components: {
    TopNav,
    TopTitle,
    Social,
    Contact,
    CopyRight
  },

  data() {
    return {
      mouse: {
        x: 0,
        y: 0
      },
      icon: {
        x: 0,
        y: 0,
        left: 0,
        top: 0,
      },
    };
    
  },

  mounted() {
    this.$nextTick(this.followMouse);
  },

  methods: {

    followMouse() {

      const $ = document.querySelector.bind(document);
      const $on = document.addEventListener.bind(document);
      
      var mouseIconSquare = $('#mouse-icon-square');
      var mouseIconCircle = $('#mouse-icon-circle');

      var mouseData = this.mouse;
      var iconData = this.icon;

      const tm = this.$gsap.TweenMax;
      const ease = this.$gsap.Linear.easeNone;

      let mouseIsMove = false;

      $on('mousemove', mouseMoved);
      function mouseMoved (e) {
        mouseData.x = e.clientX || e.pageX;
        mouseData.y = e.clientY || e.pageY;
        if (!iconData.x || !iconData.y || mouseIsMove) {
          iconData.x = mouseData.x;
          iconData.y = mouseData.y;
        };
        tm.to(mouseIconCircle, .3, { x: iconData.x, y: iconData.y, ease: ease });
        mouseIsMove = true;
      }


      // Create a new Timeline (equivalent to new TimelineMax())
      // const tl = new this.$gsap.TimelineMax()

      // tl
      //   .to(mouseIconCircle, 1, { x: 200, y: 200, ease: this.$gsap.Linear.easeNone })
        // .to(mouseIconSquare, 1, { x: 5, y: 5, ease: this.$gsap.Linear.easeNone });

    //   var $ = document.querySelector.bind(document);
    //   var $on = document.addEventListener.bind(document);

    //   var mouseX, mouseY;
    //   $on('mousemove', function (e) {
    //     mouseX = e.clientX || e.pageX;
    //     mouseY = e.clientY || e.pageY;
        
    //     var ball = $('#ball');
        
    //     var x = void 0, y = void 0, dx = void 0, dy = void 0, tx = 0, ty = 0, key = -1;

    //       // key = requestAnimationFrame(followMouse);

    //       if(!x || !y) {
    //         x = mouseX;
    //         y = mouseY;
    //       }else {
    //         dx = (mouseX - x) * 0.125;
    //         dy = (mouseY - y) * 0.125;

    //         if(Math.abs(dx) + Math.abs(dy) < 0.1) {
    //           x = mouseX;
    //           y = mouseY;
    //         }else {
    //           x += dx;
    //           y += dy;
    //         }
    //       }

    //       ball.style.left = x + 'px';
    //       ball.style.top = y + 'px';
    //       ball.style.visibility = "visible";

    //   });
    },
  },

}
</script>

<style scped>
.default {
  overflow: hidden;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
}
.default-container {
  height: 100%;
  width: 100%;
}
.default-bg {
  height: 100%;
  width: 100%;
}
.default-container .default-bg::before, .default-container .default-bg::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.default-container .default-bg::before {
  height: 100%;
  width: 100%;
  opacity: .15;
  background: url('/img/bg/fg_texture-2.png') repeat 50%/130px 130px;
}
.default-container .default-bg::after {
  height: 100%;
  width: 100%;
  opacity: .25;
  background: url('/img/bg/bg_canvas-repeat-3-white.png') repeat 50%/350px 200px;
}
.pages-content {
  margin-top: 5vw;
}

.mouse-icon-circle {
  position: absolute;
  z-index: 1;
  background: transparent;
  margin-left: -30px;
  width: 20px;
  height: 20px;
  border: 2px solid #816f19;
  border-radius: 50%;
  box-shadow: 0px 0px 2px 2px rgba(255,255,255, 0.2);
}
.mouse-icon-square {
  position: absolute;
  display: block;
  top: 50%;
  left: 50%;
  width: 3px;
  height: 3px;
  transform: translate(-50%, -50%);
  display: block;
  background: #999999;
  box-shadow: 0px 0px 1px 1px rgba(255,255,255, 0.3);
}

</style>

