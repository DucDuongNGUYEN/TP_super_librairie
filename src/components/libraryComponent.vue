<!-- libraryComponent.vue -->
<template>
  <ul class="grid">
    <li class="game" v-for="game in games" :key="game.title" :class="game.type">
      <img :src="game.imageSource" width="200" height="200">
      <div class="image-text">{{ game.title }}</div>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    games: {
      type: Array,
      required: true
    }
  }
}
</script>
<style scoped>
.grid {
  display: grid;
  list-style-type: none;
  grid-template-columns: repeat(4, 250px);
  grid-template-rows: repeat(3, 250px);
  gap: 35px;
  padding: 50px 0px 35px 190px;
  text-align: center;
  margin: auto;
  width: auto;
}

img {
  display: block;
  border-radius: 8px;
  box-shadow: 6px 6px;
  transition: transform 1s ease-in-out;
  transition-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
}

li {
  position: relative;
  width: 50%;
}

ul li:hover {
  size: 200px;
  margin: 0;
  transform: scale(1.2);
}

li:hover .image-text {
  opacity: 1;
}

.image-text {
  position: absolute;
  bottom: 0px;
  background: rgba(0, 0, 0, 0.5);
  width: 13rem;
  transition: all 0.5s ease 0s;
  opacity: 0.8;
  color: white;
  font-size: 20px;
  padding: 20px;
  text-align: center;
  translate: -1px -50px;
  border-radius: 0 0 8px 8px;
}
</style>  