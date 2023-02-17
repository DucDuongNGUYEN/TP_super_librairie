<!-- filterComponent.vue -->
<template>
  <div>
    <h2>Filtres :</h2>
    <h3>Players</h3>
    <form>
      <label>
        <input type="checkbox" v-model="soloChecked"> Solo<br />
      </label>
      <label>
        <input type="checkbox" v-model="multijoueurChecked"> Multijoueur
      </label>
    </form>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      soloChecked: false,
      multijoueurChecked: false
    }
  },
  watch: {
    soloChecked: function () {
      this.$emit('filter', { solo: this.soloChecked, multijoueur: this.multijoueurChecked });
    },
    multijoueurChecked: function () {
      this.$emit('filter', { solo: this.soloChecked, multijoueur: this.multijoueurChecked });
    }
  }
}
</script>
