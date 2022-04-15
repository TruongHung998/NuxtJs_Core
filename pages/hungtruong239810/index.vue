<template lang="pug">
  .container
    .intro-container
      .intro-wrap
        .sharp-wrap
          .sharp-wrap-height
            .sharp-style
              .style-asset
                img(:src="'/sharp1.png'").sharp-1
        .content-container
          .content-container-1
            .wrap-title
              .title-1.line1
                .title-black-1 I AM  &nbsp
                .title-color HUNGTRUONG
                .title-black-1  &nbsp AND
              .title-2.line2
                .title-black THIS IS WHAT I DO BEST
          .content-container-2
            .content
              .container
              .content-container-2-wrap
                .wrap-1
                  .title mình đang làm gì? ...
                  .text-content {{ '  Hiện tại mình đang là Software engineer tại Eco Pharma. Web App & Mobile cross platform là những thứ mà mình đang làm hiện tại \n  Mình có 2 năm kinh nghiệm trong phát triển phần mềm, đặc biệt là trong ngành chăm sóc khách hàng, ecommerce, medtech' }}
                .wrap-2
                  .title-react-native React Native
                  .text-content {{ '  Mình sử dụng React Native để phát triển ứng dụng trên cả 2 hệ điều hành ios và android \n  Có kinh nghiệm trong việc xử lý thanh toán online,Animation, UI - UX của mobile, notification, tối ưu hiệu năng trên 2 hệ điều hành và nhiều thứ khác ...' }}
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
      "border-right-color": "#708E79"
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
        gsap.to(".sharp-wrap-height", {
          height: '80vh',
        });
        gsap.to(".sharp-1", {
          duration: 0.3,
          ease: 'none',
          transform: 'rotate(-4.9998deg) rotateY(-34.6405deg) rotateX(17.2363deg)',
        });
        gsap.set('.sharp-1', {
          attr: {src: '/sharp1.png'},
          ease: 'none'
        });
      }
    })
    // TODO: container-2

    ScrollTrigger.create({
      trigger: '.content-container-2-wrap',
      start: "top 70%",
      end: 'bottom 50%',
      onEnter: function () {
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
          duration: 0.3,
          ease: 'none',
          x: -_width * 0.42,
          transform: 'rotateY(35deg) rotateX(10deg)',
        });
        gsap.set('.sharp-1', {
          attr: {src: '/sharp2.png'},
          ease: 'none'
        });
        gsap.to(".sharp-wrap-height", {
          height: '100vh',
        });
      },
      onLeave: function () {
        gsap.fromTo('.wrap-1', {autoAlpha: 1}, {autoAlpha: 0, overwrite: "auto"});
      },
      onEnterBack: function () {
        gsap.to(".sharp-1", {
          duration: 0.3,
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
      },
      onLeaveBack: function () {
        gsap.fromTo('.wrap-1', {autoAlpha: 1}, {autoAlpha: 0, overwrite: "auto"});
      }
    });

    // TODO: container-3

    ScrollTrigger.create({
      trigger: '.content-container-3-wrap',
      start: "top 70%",
      end: 'bottom 50%',
      onEnter: function () {
        gsap.to(".sharp-1", {
          duration: 0.3,
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
