<template lang="pug">
  .main-container
    .header-container
      img(:src="'/Frame 2.png'").header-image
    .header-bar(:class="{change_color: scrollPosition > 50}")
      .title1 @hungtruong239810
      .menu-container__header-bar
        .group-icon
          button
            i.bx.bxl-facebook-square.icon-button
          button
            i.bx.bxl-instagram-alt.icon-button
          button
            i.bx.bxl-linkedin-square.icon-button
        .group-button
          el-dropdown.dropdown-button
            .title-button Work
            el-dropdown-menu(slot="dropdown")
              el-dropdown-item Application
              el-dropdown-item Web Application
          el-dropdown.dropdown-button
            .title-button Ngôn ngữ
            el-dropdown-menu(slot="dropdown")
              el-dropdown-item Việt Nam
              el-dropdown-item Tiếng Anh
        .switch-lang
          i.bx.bx-moon
          el-switch(v-model='language' active-color="#708E79"
            inactive-color="#CED2BD").switch--style
          i.bx.bx-sun
    .avatar-container
      img(:src="'/avatar.png'").main-avatar
</template>

<script>
import {gsap} from "gsap";

export default {
  data() {
    return {
      language: true,
      scrollPosition: null
    }
  },
  computed: {
    title() {
      return 'My life going on'
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
  width: 300px;
  height: 300px;
  border-radius: 150px;
  position: absolute;
  bottom: -38%;
  background: white;
  left: 43%;
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
  height: 350px;
  width: 100%;
  position: relative;
  @media screen and (min-width: 2600px) {
    height: 450px;
  }
}

.header-container {
  height: 350px;
  width: 100%;

  .content__header-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
  }

  .header-image {
    height: 350px;
    object-fit: cover;
    width: 100%;
    content: '';
    z-index: -1;
    @media screen and (min-width: 1600px) {
      object-position: 0 -200px;
    }
    @media screen and (min-width: 1800px) {
      object-position: 0 -250px;
    }
    @media screen and (min-width: 2600px) {
      height: 450px;
      object-position: 0 -450px;
    }
  }
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
    background: black;
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
    width: 50%;
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

    .group-icon {
      display: flex;
      justify-content: space-around;
    }
  }
}
</style>
