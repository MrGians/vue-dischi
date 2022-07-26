<template>
  <header>
    <div id="navbar">
      <div class="container-lg">
        <img src="./../assets/img/logo.svg" alt="Spotify Logo" />
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "BaseHeader",
};
</script>

<style lang="scss" scoped>
@import "./../assets/scss/style.scss";
header {
  height: 50px;
  padding: 0.5rem;
  background-color: $primary_color;

  #navbar {
    img {
      width: 100px;
      height: 100%;
      filter: invert(66%) sepia(61%) saturate(632%) hue-rotate(85deg) brightness(94%) contrast(86%);
    }
  }
}
</style>
