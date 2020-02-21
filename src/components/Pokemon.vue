<template>
  <div class="pokemon">
    <h2>
      {{ name }}
    </h2>
  </div>
</template>

<script>
export default {
  name: "Pokemon",
  props: {
    name: String,
    type: String
  }
};
</script>

<style>
.pokemon {
  padding: 10px;
  border: 1px solid #808080;
  border-radius: 10px;
  margin-bottom: 10px;
  width: 30vw;
}
</style>
