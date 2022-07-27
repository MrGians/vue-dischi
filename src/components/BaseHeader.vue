<template>
  <header>
    <div class="container-lg">
      <div id="navbar">
        <img src="./../assets/img/logo.svg" alt="Spotify Logo" />
        <div class="search-filters">
          <!-- Disc Genre Select -->
          <BaseSelect
            @selected-value="selectedGenreValue"
            :options="genreList"
            custom-option="Seleziona un genere"
          />
          <!-- Artist Name Select -->
          <BaseSelect
            @selected-value="selectedArtistValue"
            :options="artistList"
            custom-option="Seleziona un artista"
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
    artistList: Array,
  },
  methods: {
    selectedGenreValue(value) {
      console.log(2, value);
      this.$emit("selected-genre-value", value);
    },
    selectedArtistValue(value) {
      console.log(2, value);
      this.$emit("selected-artist-value", value);
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
    .search-filters {
      display: flex;
    }
  }
}
</style>
