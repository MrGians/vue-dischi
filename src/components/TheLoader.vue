<template>
  <div class="loader">
    <strong>Discs List is loading...</strong>
  </div>
</template>

<script>
export default {
  name: "TheLoader",
};
</script>

<style lang="scss" scoped>
.loader {
  height: calc(100vh - 50px);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 5rem;
  color: white;
}
</style>
