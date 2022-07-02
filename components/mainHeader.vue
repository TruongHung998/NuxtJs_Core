<template lang="pug">
  .main-container
    //.header-bar(:class="{change_color: scrollPosition > 50}")
    //  .menu-container__header-bar
    //    .group-icon
    //      button
    //        i.bx.bxl-facebook-square.icon-button
    //      button
    //        i.bx.bxl-instagram-alt.icon-button
    //      button
    //        i.bx.bxl-linkedin-square.icon-button
    //    .group-button
    //      //el-dropdown.dropdown-button
    //      //  .title-button Work
    //      //  el-dropdown-menu(slot="dropdown")
    //      //    el-dropdown-item Application
    //      //    el-dropdown-item Web Application
    //      el-dropdown.dropdown-button
    //        .title-button SaiGon
    //    .switch-lang
    //      .lang EN
    //      el-switch(v-model='language' active-color="#1C96BA"
    //        inactive-color="#CED2BD").switch--style
    //      .lang VN
    //.avatar-container
    //  img(:src="'/avatar.png'").main-avatar
</template>

<script>
import {gsap} from "gsap";
import {killTriggerGsap} from "@/helper/util";

export default {
  data() {
    return {
      language: true,
      scrollPosition: null
    }
  },
  computed: {
    title() {
      return 'Portfolio'
    }
  },
  head() {
    return {
      title: this.title
    }
  },
  mounted() {
    gsap.from('.main-avatar', {
      ease: 'none',
      duration: 1,
      opacity: 0
    });
    window.addEventListener('scroll', this.updateScroll);
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY
    }
  }
}
</script>

<style lang="scss" scoped>
.avatar-container {
  width: 250px;
  height: 250px;
  border-radius: 15vw;
  position: absolute;
  bottom: -40%;
  background: white;
  left: 45%;
  display: flex;
  justify-content: center;
  align-items: center;

  .main-avatar {
    width: 97%;
    height: 97%;
    border-radius: 50%;
    object-fit: cover;
    will-change: contents;
  }
}

.main-container {
  height: 60px;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
}

.header-bar {
  width: 100%;
  height: 60px;
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 100;

  &.change_color {
    background: linear-gradient(301.39deg, #000000 -54.66%, #315875 70.89%, rgba(82, 70, 131, 0.901042) 106.94%, rgba(255, 255, 255, 0) 184.01%);
  }

  .title1 {
    font-size: 2em;
    color: white;
    font-weight: bold;
    padding-left: 2rem;
    cursor: pointer;
  }

  .menu-container__header-bar {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    height: 100%;
    width: 100%;
    padding-right: 1rem;

    .icon-button {
      color: white;
      font-size: 2rem;
    }

    .title-button {
      font-size: 1.1rem;
      color: white;
      font-weight: bold;
    }

    .title-lang {
      font-size: .8rem;
      color: white;
      font-weight: bold;
    }

    .switch-lang {
      margin-left: 2rem;
      display: flex;
      align-items: center;

      i {
        color: white;
        font-size: 20px;
      }
    }

    .switch--style {
      margin: 0 1rem;
    }

    .dropdown-button {
      cursor: pointer;
    }

    .group-button {
      display: flex;
      align-items: center;
      justify-content: space-around;
      margin-left: 2rem;

      > * {
        margin: 0 1rem;
      }
    }
    .lang {
      color: white;
      font-weight: bold;
      font-size: .8rem;
    }

    .group-icon {
      display: flex;
      justify-content: space-around;
    }
  }
}
</style>
