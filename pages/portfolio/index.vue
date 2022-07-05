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
                  img(:src="'/sharp1.png'").item-2
                  img(:src="'/sharp1.png'").item-3
        .absolute-view
          .line-absolute
          .line-absolute
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
                  .wrap-absolute
                    .wrap-line
                      img(:src="'/curveline.png'").curve-line
                    .content-box
                      .content-box-1
            //.content-container-3
            //  .content
            //    .content-container-3-wrap
            //    .container
    //.body-content
    //  .list-content
</template>

<script>
import {gsap} from 'gsap/all'
import {handleHomeAnimation, killTriggerGsap} from "@/helper/util";


export default {
  data() {
    return {
      windowTop: 0
    }
  },
  mounted() {
    handleHomeAnimation()
  },
  created() {
    window.addEventListener("resize", this.myEventHandler);
  },
  destroyed() {
    window.removeEventListener("resize", this.myEventHandler);
  },
  methods: {
    myEventHandler() {
      killTriggerGsap()
      handleHomeAnimation()
    },
  }
}
</script>

<style lang="scss" scoped>
@import "./style";
</style>
