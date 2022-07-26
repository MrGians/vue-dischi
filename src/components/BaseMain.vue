<template>
  <main>
    <!-- Loader -->
    <TheLoader v-if="discsList.length !== 10" />
    <!-- Discs List -->
    <div v-else id="discs-list">
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
import TheLoader from "./TheLoader.vue";
export default {
  name: "BaseMain",
  components: { DiscCard, TheLoader },
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
