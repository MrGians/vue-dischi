<template>
  <main>
    <div id="discs-list">
      <div class="container">
        <div class="row py-5">
          <div v-for="disc in discsList" :key="disc.title" class="col py-3">
            <DiscCard :disc="disc" />
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";
export default {
  name: "BaseMain",
  components: { DiscCard },
  props: {
    discsList: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "./../assets/scss/style.scss";

#discs-list {
  .container {
    max-width: 800px;

    .col {
      flex-basis: 20%;
      flex-grow: 0;
    }
  }
}
</style>
