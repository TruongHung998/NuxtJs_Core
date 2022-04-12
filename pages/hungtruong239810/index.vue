<template lang="pug">
  .container
    img(:src="'/mainTitle.png'").main-title-img
    .intro-container
      .intro-wrap
        .sharp-wrap
          .sharp-style
            .style-asset
              img(:src="'/sharp1.png'").sharp-1
        .content-container
          img(:src="'/content1.png'").content-1
        .content-container
          img(:src="'/content2.png'").content-2
        .content-container
          img(:src="'/content3.png'").content-3
    .body-content
      .content
</template>

<script>
import {gsap} from 'gsap'

export default {
  data() {
    return {
      windowTop: 0
    }
  },
  mounted() {
    gsap.to(".sharp-1", {
      transform: 'rotateY(35deg) rotateX(10deg)',
    });
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
        console.log(val)
        switch (true) {
          case val < 710:
            gsap.to(".sharp-1", {
              transform: 'rotateY(35deg) rotateX(10deg)',
            });
            gsap.set('.sharp-1', {
              attr: {src: '/sharp1.png'},
              ease: 'none',
              duration: 0.3,
            });
            break
          case val < 1550:
            gsap.to(".sharp-1", {
              duration: 0.3,
              ease: 'none',
              x: 400,
              transform: 'rotate(-6.0001deg) rotateY(-39.6407deg) rotateX(27.2366deg)',
            });
            gsap.set('.sharp-1', {
              attr: {src: '/sharp2.png'},
              ease: 'none',
              duration: 0.3,
            });
            break
          case val >= 1550:
            gsap.to(".sharp-1", {
              duration: 0.3,
              ease: 'none',
              transform: 'rotateY(35deg) rotateX(10deg)',
            });
            gsap.set('.sharp-1', {
              attr: {src: '/sharp3.png'},
              ease: 'none',
              duration: 0.3,
            });
            break
        }
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
