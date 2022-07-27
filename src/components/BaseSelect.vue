<template>
  <select @change="setOptionValue">
    <option value="" selected>{{ customOption }}</option>
    <option v-for="option in options" :key="option" :value="option">
      {{ option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "BaseSelect",
  props: {
    options: Array,
    customOption: String,
  },
  methods: {
    setOptionValue(event) {
      console.log(1, event.target.value);
      this.$emit("selected-value", event.target.value);
    },
  },
};
</script>
