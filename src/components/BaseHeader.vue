<template>
  <header>
    <div class="container-lg">
      <div id="navbar">
        <img src="./../assets/img/logo.svg" alt="Spotify Logo" />
        <div class="search-filters">
          <BaseSelect
            @selected-value="selectedValue"
            :options="genreList"
            custom-option="Seleziona un genere"
          />
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import BaseSelect from "./BaseSelect.vue";
export default {
  name: "BaseHeader",
  components: { BaseSelect },
  props: {
    genreList: Array,
  },
  methods: {
    selectedValue(value) {
      console.log(2, value);
      this.$emit("selected-value", value);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "./../assets/scss/style.scss";
header {
  height: 50px;
  padding: 0.5rem;
  background-color: $secondary_color;

  #navbar {
    display: flex;
    justify-content: space-between;

    img {
      width: 100px;
      height: 100%;
      filter: invert(66%) sepia(61%) saturate(632%) hue-rotate(85deg) brightness(94%) contrast(86%);
    }
  }
}
</style>
