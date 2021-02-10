<template>
  <div class="prof-pic-wrapper" :style="{width: size}">
    <div class="prof-pic-sizer"></div>
    <img class="prof-pic-img" src="@/assets/cougar_prof.png" />
  </div>
</template>

<script>
export default {
  name: 'ProfPic',
  props: {
    size: String
  }
}
</script>

<style scoped>
.prof-pic-wrapper {
  position: relative;
  overflow: hidden;
  width: 50px;
  border-radius: 50%;
  border: 3px solid #fff;
}

.prof-pic-img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
}

.prof-pic-sizer {
  width: 100%;
  padding-top: 100%;
}
</style>
