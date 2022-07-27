<template>
  <main>
    <!-- Loader -->
    <TheLoader v-if="discsList.length !== 10" />
    <!-- Discs List -->
    <div v-else id="discs-list">
      <div class="container">
        <div class="row py-3">
          <div v-for="disc in filteredDiscsList" :key="disc.title" class="col py-3">
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
    selectedGenreValue: String,
    selectedArtistValue: String,
  },
  computed: {
    filteredDiscsList() {
      // SE Entrambe le stringe sono vuote
      if (!this.selectedGenreValue && !this.selectedArtistValue) return this.discsList;

      // SE solo il valore "Genere" è stato selezionato
      if (this.selectedGenreValue && !this.selectedArtistValue) {
        return this.discsList.filter((disc) => {
          return disc.genre.toLowerCase() === this.selectedGenreValue;
        });
      }
      // SE solo il valore "Artista" è stato selezionato
      else if (!this.selectedGenreValue && this.selectedArtistValue) {
        return this.discsList.filter((disc) => {
          return disc.author.toLowerCase() === this.selectedArtistValue;
        });
      }
      // SE i valori "Genere" & "Artista" sono stati entrambi selezionati
      return this.discsList.filter((disc) => {
        return (
          disc.genre.toLowerCase() === this.selectedGenreValue &&
          disc.author.toLowerCase() === this.selectedArtistValue
        );
      });
    },
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
