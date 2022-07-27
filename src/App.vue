<template>
  <div>
    <BaseHeader @selected-value="setSelectedValue" :genre-list="genreList" />
    <BaseMain :selected-value="selectedValue" :discs-list="discsList" />
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
        });
      });
    },
    setSelectedValue(value) {
      this.selectedValue = value.toLowerCase();
    },
  },
  data() {
    return {
      endPoint: "https://flynn.boolean.careers/exercises/api/array/music",
      discsList: [],
      genreList: [],
      selectedValue: "",
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
