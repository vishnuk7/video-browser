<template>
  <div>
    <input class="form-control" id="search" type="text" @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput(event) {
      this.$emit("termChange", event.target.value);
    }
  }
};
</script>

<style scoped>
#search {
  width: 100%;
  margin-top: 2rem;
  border-radius: 20px;
}
</style>
