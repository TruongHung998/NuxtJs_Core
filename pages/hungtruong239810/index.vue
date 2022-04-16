<template lang="pug">
  .container
    MainHeader
    .intro-container
      .intro-wrap
        .sharp-wrap
          .sharp-wrap-height
            .sharp-style
              .style-asset
                .sharp-1
                  img(:src="'/sharp1.png'").item-1
                  img(:src="'/sharp2.png'").item-2
                  img(:src="'/sharp3.png'").item-3
        .content-container
          .content-container-1
            .wrap-title
              .title-1.line1
                .title-black-1 I AM  &nbsp
                .title-color HUNGTRUONG
                .title-black-1  &nbsp AND
              .title-2.line2
                .title-black THIS IS WHAT I DO BEST
          .wrap-container
            .content-container-2
              .content
                .container
                .content-container-2-wrap
                  .wrap-1
                    .title {{ 'Mình đang \n       làm gì? ...' }}
                    .text-content {{ '  Hiện tại mình đang là Software engineer tại Eco Pharma. Web App & Mobile cross platform là những thứ mà mình đang làm hiện tại \n  Mình có 2 năm kinh nghiệm trong phát triển phần mềm, đặc biệt là trong ngành chăm sóc khách hàng, ecommerce, medtech, ...' }}
              img(:src="'/polygon1.png'").polygon-1
              img(:src="'/sticker-1.png'").sticker-1
            .content-container-3
              .content
                .content-container-3-wrap
                .container
    .body-content
      .list-content
</template>

<script>
import {gsap, SteppedEase, TimelineMax} from 'gsap/all'
import {ScrollTrigger} from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

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
      width: "26em", /* same as CSS .line-1 width */
      ease: SteppedEase.config(50)
    }, 0);
    // text cursor animation
    tl.fromTo(".line1", 1, {
      "border-right-color": "#0C73B2"
    }, {
      "border-right-color": "rgba(255,255,255,0)",
      repeat: -1,
      ease: SteppedEase.config(30)
    }, 0);

    tl.play();

    setTimeout(() => {
      gsap.set(".title-black", {
        opacity: 1,
      })
    }, 1000)
    const _height = window.innerHeight
    const _width = window.innerWidth
    gsap.to(".sharp-1", {
      transform: 'rotate(-4.9998deg) rotateY(-34.6405deg) rotateX(17.2363deg)',
      duration: 2
    });

    // TODO: container-1

    ScrollTrigger.create({
      trigger: '.content-container-1',
      start: "top 70%",
      end: 'bottom 50%',
      onEnterBack: function () {
        gsap.to(".sharp-1", {
          duration: 0.4,
          ease: 'none',
          transform: 'rotate(-4.9998deg) rotateY(-34.6405deg) rotateX(17.2363deg)',
        });
        gsap.set('.sharp-1', {
          attr: {src: '/sharp1.png'},
          ease: 'none'
        });
        gsap.to(".item-1", {
          duration: 0.2,
          ease: 'none',
          autoAlpha: 1
        });
        gsap.to(".item-2", {
          duration: 0.2,
          ease: 'none',
          autoAlpha: 0
        });
      }
    })
    // TODO: container-2

    ScrollTrigger.create({
      trigger: '.content-container-2-wrap',
      start: "top 70%",
      end: 'bottom 50%',
      onEnter: function () {
        gsap.to(".item-2", {
          ease: 'none',
          duration: 0.2,
          autoAlpha: 1,
          display: 'block'
        });
        gsap.to(".item-1", {
          ease: 'none',
          duration: 0.2,
          autoAlpha: 0
        });
        gsap.fromTo(
            '.wrap-1',
            {y: 100, autoAlpha: 0},
            {
              duration: 1.25,
              y: 0,
              autoAlpha: 1,
              ease: "back",
              overwrite: "auto"
            }
        );
        gsap.to(".sharp-1", {
          duration: 0.4,
          ease: 'none',
          x: -_width * 0.42,
          transform: 'rotateY(35deg) rotateX(10deg)',
        });
        gsap.set('.sharp-1', {
          attr: {src: '/sharp2.png'},
          ease: 'none'
        });
        gsap.fromTo(".polygon-1", {
          x: -400,
          autoAlpha: 0,
        }, {
          duration: 1.25,
          ease: 'back',
          x: 0,
          autoAlpha: 1,
        });
        gsap.fromTo(".sticker-1", {
          x: 400,
          autoAlpha: 0,
        }, {
          duration: 1.25,
          ease: 'back',
          x: 0,
          autoAlpha: 1,
        });
      },
      onLeave: function () {
        gsap.fromTo(".polygon-1", {
          x: 0,
          autoAlpha: 1,
        }, {
          duration: 1.25,
          ease: 'back',
          x: -400,
          autoAlpha: 0,
        });
        gsap.fromTo(".sticker-1", {
          x: 0,
          autoAlpha: 1,
        }, {
          duration: 1.25,
          ease: 'back',
          x: 400,
          autoAlpha: 0,
        });
        gsap.fromTo('.wrap-1', {autoAlpha: 1}, {autoAlpha: 0, overwrite: "auto"});
      },
      onEnterBack: function () {
        gsap.to(".item-2", {
          ease: 'none',
          duration: 0.2,
          autoAlpha: 1,
          display: 'block'
        });
        gsap.to(".item-3", {
          ease: 'none',
          duration: 0.2,
          autoAlpha: 0
        });
        gsap.to(".sharp-1", {
          duration: 0.4,
          ease: 'none',
          x: -_width * 0.42,
          transform: 'rotateY(35deg) rotateX(10deg)',
        });
        gsap.set('.sharp-1', {
          attr: {src: '/sharp2.png'},
          ease: 'none'
        });
        gsap.fromTo(
            '.wrap-1',
            {y: -100, autoAlpha: 0},
            {
              duration: 1.25,
              y: 0,
              autoAlpha: 1,
              ease: "back",
              overwrite: "auto"
            }
        );
        gsap.fromTo(".polygon-1", {
          x: -400,
          autoAlpha: 0,
        }, {
          duration: 1.25,
          ease: 'back',
          x: 0,
          autoAlpha: 1,
        });
        gsap.fromTo(".sticker-1", {
          x: 400,
          autoAlpha: 0,
        }, {
          duration: 1.25,
          ease: 'back',
          x: 0,
          autoAlpha: 1,
        });
      },
      onLeaveBack: function () {
        gsap.to(".polygon-1", {
          duration: 1.25,
          ease: 'back',
          x: -400,
        });
        gsap.to(".polygon-1", {
          duration: 1.25,
          ease: 'back',
          x: -400,
        });
        gsap.fromTo(".sticker-1", {
          x: 0,
          autoAlpha: 1,
        }, {
          duration: 1.25,
          ease: 'back',
          x: 400,
          autoAlpha: 0,
        });
      }
    });

    // TODO: container-3

    ScrollTrigger.create({
      trigger: '.content-container-3-wrap',
      start: "top 70%",
      end: 'bottom 50%',
      onEnter: function () {
        gsap.to(".item-3", {
          ease: 'none',
          duration: 0.2,
          autoAlpha: 1,
          display: 'block'
        });
        gsap.to(".item-2", {
          ease: 'none',
          duration: 0.2,
          autoAlpha: 0
        });
        gsap.to(".sharp-1", {
          duration: 0.4,
          ease: 'none',
          transform: 'rotate(-4.9998deg) rotateY(-34.6405deg) rotateX(17.2363deg)',

        });
        gsap.set('.sharp-1', {
          attr: {src: '/sharp3.png'},
          ease: 'none'
        });
      }
    })
  }
}
</script>

<style lang="scss" scoped>
@import "./style";
</style>
