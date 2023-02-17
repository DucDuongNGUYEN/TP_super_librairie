<!-- sortComponent.vue -->
<template>
  <div class="sort">
    <h2>Tri :</h2>
    <select v-model="sortDirection">
      <option value="asc">Ordre alphabétique</option>
      <option value="desc">Ordre alphabétique inverse</option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sortDirection: 'asc'
    }
  },
  watch: {
    sortDirection: function () {
      this.$emit('sort', this.sortDirection);
    }
  }
}
</script>