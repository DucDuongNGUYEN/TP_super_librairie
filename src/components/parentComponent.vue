<template>
  <div class="body">
    <header class="header">
      <h1>Notre super bibliothèque</h1>
    </header>
    <div class="sidebar">
      <filterComponent @filter="handleFilter" />
      <sortComponent @sort="handleSort" />
    </div>
    <div class="article">
      <libraryComponent :games="filteredGames" />
    </div>
  </div>
</template>

<script>
import filterComponent from './filterComponent.vue';
import sortComponent from './sortComponent.vue';
import libraryComponent from './libraryComponent.vue';

export default {
  components: {
    filterComponent,
    sortComponent,
    libraryComponent
  },
  data() {
    return {
      games: [
        {
          title: 'Princess not found',
          type: 'solo',
          imageSource: require('@/assets/images/image1.png')
        },
        {
          title: 'Le chapelier fou',
          type: 'solo',
          imageSource: require('@/assets/images/image2.png')
        },
        {
          title: 'Dab Simulator',
          type: 'multijoueur',
          imageSource: require('@/assets/images/image3.png')
        },
        {
          title: 'League of woof',
          type: 'multijoueur',
          imageSource: require('@/assets/images/image4.jpg')
        },
        {
          title: 'Overwatch 1.2',
          type: 'multijoueur',
          imageSource: require('@/assets/images/image5.jpg')
        },
        {
          title: 'Le ouicheur 4',
          type: 'solo',
          imageSource: require('@/assets/images/image6.png')
        },
        {
          title: 'Chill/20',
          type: 'solo',
          imageSource: require('@/assets/images/image7.jpg')
        },
        {
          title: 'Tomber dehors 3',
          type: 'solo',
          imageSource: require('@/assets/images/image8.png')
        },
        {
          title: 'Jump here',
          type: 'solo',
          imageSource: require('@/assets/images/image9.png')
        },
        {
          title: 'Call of duty',
          type: 'multijoueur',
          imageSource: require('@/assets/images/image10.jpg')
        },
        {
          title: 'Fifa 23',
          type: 'multijoueur',
          imageSource: require('@/assets/images/image11.jpg')
        },
        {
          title: 'Pubg',
          type: 'multijoueur',
          imageSource: require('@/assets/images/image12.png')
        },
      ],
      filteredGames: [],
      sortDirection: 'asc'
    }
  },
  created() {
    this.filteredGames = this.games;
  },
  methods: {
    handleFilter(filter) {
      this.filteredGames = this.games.filter(game => {
        return (game.type === 'solo' && filter.solo) || (game.type === 'multijoueur' && filter.multijoueur);
      });
    },
    handleSort(sortDirection) {
      this.sortDirection = sortDirection;
      this.filteredGames.sort((a, b) => {
        if (a.title < b.title) {
          return this.sortDirection === 'asc' ? -1 : 1;
        }
        if (a.title > b.title) {
          return this.sortDirection === 'asc' ? 1 : -1;
        }
        return 0;
      });
    }
  }
}
</script>
<style>
* {
  box-sizing: border-box;
}

.header {
  background-color: rgb(103, 92, 92);
  text-align: center;
  font-size: 20px;
  font-family: 'Verdana';
  color: white;
  margin: 0;
  padding: 15px 15px;
  width: auto;
}

/* Sidebar styles */
.sidebar {
  float: left;
  background-color: rgb(63, 55, 55);
  height: 903px;
  padding: 15px 20px;
}

/* Background color */
.body {
  background-color: rgb(49, 47, 47);
  margin: -8px;
}

label,
h2,
h3 {
  color: white;
}

.article {
  padding: 0;
  border: 0;
}
</style>
