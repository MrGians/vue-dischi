<template>
  <main>
    <div id="discs-list">
      <div class="container">
        <div class="row py-5">
          <div class="col py-3">
            <!-- TODO Component Card -->
            <div class="disc-card">
              <img
                src="https://images-na.ssl-images-amazon.com/images/I/41JD3CW65HL.jpg"
                alt="test"
              />
              <h6 class="disc-name">New Jersey</h6>
              <div class="artist">Bon Jovi</div>
              <div class="date">1998</div>
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
