<template>
  <div class="container header-bg-color">
      <div class="row pt-2 pb-2">
          <img src="..\assets\img\logos.png" alt="" class="logo">
      </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style lang="scss" scoped>
    .logo {
        width: 80px;
        height: 50px;
    }
    .header-bg-color {
        background-color: #2E3A46;
    }

</style>