<template lang="pug">
  .container
    img(:src="'/mainTitle.png'").main-title-img
    .content1-container
      img(:src="'/content1.png'").content-1
      img(:src="'/sharp1.png'").sharp-1
      img(:src="'/polygon1.png'").polygon-1
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  @media screen and (max-width: 1400px) {
    width: 900px;
  }
  @media screen and (max-width: 1000px) {
    width: 500px;
  }
}
.main-title-img {
  margin: 4rem 0;
  width: 100%;
}
.content1-container {
  width: 100%;
  display: flex;
  position: relative;
  .content-1 {
    width: 100%;
    margin: 0 auto;
    z-index: 9;
  }
  .sharp-1 {
    width: 55%;
    position: absolute;
    bottom: 12%;
    left: 1%;
    z-index: 10;
  }
  .polygon-1 {
    width: 40%;
    position: absolute;
    bottom: 25%;
    z-index: 1;
    left: -2%;
  }
}
</style>
