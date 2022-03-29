<template lang="pug">
  .main-container
    .header-container
      img(:src="'/Frame 2.png'").header-image
    .header-bar
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
          button
            .title-button Work
          button
            .title-button SaiGon
        .switch-lang
          .title-lang English
          el-switch(v-model='language' active-color="#708E79"
            inactive-color="#CED2BD").switch--style
          .title-lang Việt Nam
</template>

<script>
export default {
  data () {
    return {
      language: true
    }
  },
  computed: {
    title () {
      return 'My life going on'
    }
  },
  head () {
    return {
      title: this.title
    }
  }
}
</script>

<style lang="scss" scoped>
.main-container {
  height: 350px;
  width: 100%;
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
  height: 5vh;
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  .title1 {
    font-size: 2em;
    color: white;
    font-weight: bold;
    padding-left: .5rem;
    padding-top: .5rem;
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
      font-size: 3rem;
    }
    .title-button {
      font-size: 1.5rem;
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
    }
    .switch--style {
      margin: 0 1rem;
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
