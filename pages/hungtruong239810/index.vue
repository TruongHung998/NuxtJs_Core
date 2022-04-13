<template lang="pug">
  .container
    .intro-container
      .intro-wrap
        .sharp-wrap
          .sharp-wrap-height
            .sharp-style
              .style-asset
                img(:src="'/sharp1.png'").sharp-1
        .content-container-1
          .wrap-title
            .title-1.line1
              .title-black I AM  &nbsp
              .title-color HUNGTRUONG
              .title-black  &nbsp AND
            .title.line2
              .title-black THIS IS WHAT I DO BEST
        .content-container-2
    .body-content
      .list-content
</template>

<script>
import {gsap, TimelineMax, SteppedEase} from 'gsap/all'

export default {
  data() {
    return {
      windowTop: 0
    }
  },
  mounted() {
    var tl = new TimelineMax({
      paused: true
    });
    // letter animation
    tl.fromTo(".line1", 2, {
      width: "0",
    }, {
      width: "39em", /* same as CSS .line-1 width */
      ease: SteppedEase.config(50)
    }, 0);
    // text cursor animation
    tl.fromTo(".line1", 1, {
      "border-right-color": "#708E79"
    }, {
      "border-right-color": "rgba(255,255,255,0)",
      repeat: -1,
      ease: SteppedEase.config(30)
    }, 0);

    tl.play();


    gsap.to(".sharp-1", {
      transform: 'rotate(-6.0001deg) rotateY(-39.6407deg) rotateX(17.2366deg)',
      duration: 2
    });
    gsap.from(".main-title-img", {
      opacity: 0,
      x: 300,
      duration: 2
    })
    window.addEventListener("scroll", this.onScroll)
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.onScroll)
  },
  watch: {
    windowTop: {
      immediate: true,
      handler(val) {
        console.log(val)
        console.log(window.innerHeight * 0.25)
        const _height = window.innerHeight
        // switch (true) {
        //   case val < _height:
        //     gsap.to(".sharp-1", {
        //       transform: 'rotateY(35deg) rotateX(10deg)',
        //     });
        //     gsap.set('.sharp-1', {
        //       attr: {src: '/sharp1.png'},
        //       ease: 'none',
        //       duration: 0.3,
        //     });
        //     break
        //   case val < _height + _height * 1.1:
        //     gsap.to(".sharp-1", {
        //       duration: 0.3,
        //       ease: 'none',
        //       x: 400,
        //       transform: 'rotate(-6.0001deg) rotateY(-39.6407deg) rotateX(27.2366deg)',
        //     });
        //     gsap.set('.sharp-1', {
        //       attr: {src: '/sharp2.png'},
        //       ease: 'none',
        //       duration: 0.3,
        //     });
        //     break
        //   case val >= _height + _height * 1.1:
        //     gsap.to(".sharp-1", {
        //       duration: 0.3,
        //       ease: 'none',
        //       transform: 'rotateY(35deg) rotateX(10deg)',
        //     });
        //     gsap.set('.sharp-1', {
        //       attr: {src: '/sharp3.png'},
        //       ease: 'none',
        //       duration: 0.3,
        //     });
        //     break
        // }
      }
    }
  },
  methods: {
    onScroll(e) {
      this.windowTop = window.top.scrollY /* or: e.target.documentElement.scrollTop */
    }
  }
}
</script>

<style lang="scss" scoped>
@import "./style";
</style>
