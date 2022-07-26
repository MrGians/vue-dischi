<template>
  <div class="disc-card">
    <img :src="disc.poster" :alt="disc.title" />
    <h6 class="disc-name">{{ disc.title }}</h6>
    <div class="artist">{{ disc.author }}</div>
    <div class="date">{{ disc.year }}</div>
  </div>
</template>

<script>
export default {
  name: "DiscCard",
  props: {
    disc: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "./../assets/scss/style.scss";

.disc-card {
  height: 100%;
  text-align: center;
  background-color: $secondary_color;
  padding: 0.8rem;

  .disc-name {
    text-transform: uppercase;
    padding-top: 1rem;
    color: white;
  }
  .artist,
  .date {
    font-size: 0.8rem;
    font-weight: 500;
    color: rgb(119, 119, 119);
  }
  .date {
    font-size: 0.7rem;
  }
}
</style>
