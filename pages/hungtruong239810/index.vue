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
          img(:src="'/content1.png'").content-1
</template>

<script>
import { gsap } from 'gsap'
export default {
  mounted() {
    console.log('isRun')
    // gsap.set(".sharp-1", { transform: 'rotateY(35deg) rotateX(10deg)' });
  }
}
</script>

<style lang="scss" scoped>
@import "./style";
</style>
