<template>
  <div id="app" :style="appStyle">
    <!-- <svg width="1" height="300" viewBox="0,0,40,30" style="border:1px solid #cd0000;">
      <rect x="10" y="5" width="20" height="15" fill="#cd0000"/>
  </svg> -->
  <!-- <Page1 /> -->
    <transition name="fade" :leave-active-class="leaveActiveClass">
      <component :is="'Page' + page" @done="onDone"/>
    </transition>
    <transition name="fade">
      <div class="share" v-if="share" @click="share = false"></div>
    </transition>

    <transition name="fade">
      <div class="down" v-if="!daemon && page < 11"></div>
    </transition>
    <!--<audio src="static/bgm.wav" autoplay loop>-->
      <!--您的浏览器不支持 audio 标签。-->
    <!--</audio>-->
  </div>
</template>

<script>
import $ from 'jquery'
import 'jquery-touchswipe'

const components = {}
for (let i = 0; i <= 11; ++i) {
  Object.assign(components, {
    [`Page${i}`]: require(`./components/Page${i}`).default
  })
}

window.vm = {
  name: 'app',
  components,
  data() {
    return {
      page: 0,
      backgroundColor: [
        0xffffff,
        0xffd9d9,
        0xffd9d9,
        0xfff2d9,
        0xf2ffd9,
        0xd9ffd9,
        0xd9fff2,
        0xd9f2ff,
        0xd9d9ff,
        0xd9d9ff,
        0xf2d9ff,
        0xffd9f2
      ],

      leaveActiveClass: null,
      share: false,
      daemon: true
    }
  },
  computed: {
    appStyle() {
      return {
        backgroundColor: '#' + this.backgroundColor[this.page].toString(16)
      }
    }
  },
  methods: {
    next() {
      if (this.page === 2) {
        this.leaveActiveClass = 'animated animated-slow fadeOutUp'
        setTimeout(() => {
          this.leaveActiveClass = null
        }, 1000)
      }

      this.daemon = true
      this.page = Math.min(this.page + 1, this.backgroundColor.length - 1)
    },
    prev() {
      this.daemon = true
      this.page = Math.max(this.page - 1, 1)
    },
    onDone() {
      if (this.page === 8) {
        this.page = 9
      } else {
        this.daemon = false
      }
    }
  },
  mounted() {
    const onclick = e => {
      console.log(e.target)
      if (e.target.getAttribute('xlink:href') === '#btn1') {
        window.location.href = "https://weibo.com/p/1005056520152000/home?is_all=1&stat_date=201804#feedtop"
      } else if (e.target.getAttribute('xlink:href') === '#btn2' || e.target.getAttribute('class') === 'share') {
        this.share = !this.share
      } else {
        if (this.share || this.daemon) {
          return
        }
        this.next()
      }
    }

    $("body").click(onclick)

    $("body").swipe({
      // Generic swipe handler for all directions
      swipe: (event, direction, distance, duration, fingerCount, fingerData) => {
        if (distance < 20) {
          onclick(event)
          return false
        }
        if (this.share || this.daemon) {
          return
        }
        if (direction === 'up' || direction === 'left' || direction === null) {
          this.next()
        }
        if (direction === 'down' || direction === 'right') {
          this.prev()
        }
      },
      //Default is 75px, set to 0 for demo so any distance triggers swipe
      threshold: 0
    })


    $("body").keydown(e => {
      if (this.share || this.daemon) {
        return
      }
      if ([13, 32, 39, 40, 68, 83].indexOf(e.keyCode) >= 0) {
        this.next()
      } else if ([37, 38, 65, 87].indexOf(e.keyCode) >= 0) {
        this.prev()
      }
    })

    setTimeout(() => {
      this.page = 1
    }, 100)
  },
  watch: {
    daemon (val) {
      console.log(val)
    }
  }
}


export default window.vm
</script>

<style lang="scss">
  @import "styles/global";
  #app {
    width: 100vw;
    height: 100vh;
    transition: .5s;
    display: flex;
  }
  svg {
    position: absolute;
  }
  .animated-slow {
    animation-duration: 2s !important;
  }
  text {
    font-family: 'Yuanti', sans-serif;
    font-weight: 300;
  }
  .share, .down {
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
  }
  .share {
    background: rgba(white, .7) url("../static/share.png") no-repeat;
    background-size: 40vw;
    background-position: 100% 6%;
  }
  .down {
    background: url("../static/down.png") no-repeat;
    background-size: contain;
    background-position: top right;
    animation: jump 1s infinite linear;
  }
  @keyframes jump
  {
    0%, 100% {
      transform: translate3d(0, -1%, 0);
    }
    25% {
      transform: translate3d(0, 0, 0);
    }
    75% {
      transform: translate3d(0, -2%, 0);
    }
  }

</style>
