<template>
  <div>
    <BaseHeader />
    <BaseMain />
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
      });
    },
  },
  data() {
    return {
      endPoint: "https://flynn.boolean.careers/exercises/api/array/music",
      discsList: [],
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
