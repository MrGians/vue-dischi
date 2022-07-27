<template>
  <div>
    <BaseHeader
      @selected-genre-value="setSelectedGenreValue"
      :genre-list="genreList"
      @selected-artist-value="setSelectedArtistValue"
      :artist-list="artistList"
    />
    <BaseMain
      :selected-genre-value="selectedGenreValue"
      :selected-artist-value="selectedArtistValue"
      :discs-list="discsList"
    />
  </div>
</template>

<script>
import axios from "axios";
import BaseHeader from "./components/BaseHeader.vue";
import BaseMain from "./components/BaseMain.vue";

export default {
  name: "App",
  components: { BaseHeader, BaseMain },
  methods: {
    getDiscsList() {
      axios.get(this.endPoint).then((res) => {
        this.discsList = res.data.response;

        this.discsList.forEach((disc) => {
          if (!this.genreList.includes(disc.genre)) this.genreList.push(disc.genre);

          if (!this.artistList.includes(disc.author)) this.artistList.push(disc.author);
        });
      });
    },
    setSelectedGenreValue(value) {
      this.selectedGenreValue = value.toLowerCase();
    },
    setSelectedArtistValue(value) {
      this.selectedArtistValue = value.toLowerCase();
    },
  },
  data() {
    return {
      endPoint: "https://flynn.boolean.careers/exercises/api/array/music",
      discsList: [],
      genreList: [],
      artistList: [],
      selectedGenreValue: "",
      selectedArtistValue: "",
    };
  },
  mounted() {
    this.getDiscsList();
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
