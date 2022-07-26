<template>
  <main>
    <div id="discs-list">
      <div class="container">
        <div class="row py-5">
          <div v-for="disc in discsList" :key="disc.title" class="col py-3">
            <!-- TODO Component Card -->
            <div class="disc-card">
              <img :src="disc.poster" :alt="disc.title" />
              <h6 class="disc-name">{{ disc.title }}</h6>
              <div class="artist">{{ disc.author }}</div>
              <div class="date">{{ disc.year }}</div>
            </div>
            <!-- TODO -->
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: "BaseMain",
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
    }
  }
}
</style>
