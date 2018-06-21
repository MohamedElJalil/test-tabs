<template>
  <div id="app">
    <h1>Test Tab</h1>
    <div class="content">
      <tab-container :tabs="listTabs">
        <!-- TOPICS. -->
        <div slot="Topics">
          <posts-to-show :listOfPosts="dataPosts"></posts-to-show>
        </div>

        <div slot="Archives">
          <!-- ARCHIVES. -->
          <archives-to-show :listOfArchives="dataArchives"></archives-to-show>
        </div>

        <div slot="Pages">
          <!-- PAGES.-->
          <masonry-card :itemList="dataPages"></masonry-card>
        </div>
      </tab-container>
    </div>
  </div>
</template>

<script>
// Array of TABS
const TABS = ['Topics', 'Archives', 'Pages'];
// Array of objects data of TOPICS
const TOPICS = [
  {name: "HTML Techniques", numPosts: Math.floor((Math.random() * 100) + 1)},
  {name: "CSS Styling", numPosts: Math.floor((Math.random() * 100) + 1)},
  {name: "Flash Tutorials", numPosts: Math.floor((Math.random() * 100) + 1)},
  {name: "Web Miscellanea", numPosts: Math.floor((Math.random() * 100) + 1)},
  {name: "Site News", numPosts: Math.floor((Math.random() * 100) + 1)},
  {name: "Web Development", numPosts: Math.floor((Math.random() * 100) + 1)},
];
// Array of objects data of ARCHIVES
const ARCHIVES = [
  { urlImage: "https://picsum.photos/200/200/?image=960", description: "Lorem ipsum sagittis egestas felis vivamus convallis habitasse cursus ultricies." },
  { urlImage: "https://picsum.photos/200/200/?image=890", description: "Etiam et congue dolor augue cursus ultricies eleifend eu libero cubilia." },
  { urlImage: "https://picsum.photos/200/200/?image=887", description: "Aam placerat curabitur libero cubilia dui ipsum sagittis egestas felis." },
  { urlImage: "https://picsum.photos/200/200/?image=384", description: "Etiam iaculis sem ut volutpat et aptent vivamus convallis." },
  { urlImage: "https://picsum.photos/200/200/?image=691", description: "Placerat mauris et cursus ultricies aptent vivamus convallis habitasse netus." },
];
// Array of objects data of PAGES
const PAGES = [
  { urlImage: "https://picsum.photos/300/200/?image=960", title: "Cras neque elit" },
  { urlImage: "https://picsum.photos/300/300/?image=692", title: "Sagittis egestas" },
  { urlImage: "https://picsum.photos/300/150/?image=890", title: "Suspendisse" },
  { urlImage: "https://picsum.photos/300/100/?image=886", title: "Curabitur libero" },
  { urlImage: "https://picsum.photos/300/250/?image=387", title: "Volutpat et aptent" },
  { urlImage: "https://picsum.photos/300/168/?image=633", title: "Cursus ultricies" },
  { urlImage: "https://picsum.photos/300/300/?image=676", title: "Ultricies aptent" },
];

// Import components to use
import TabContainer from './components/TabContainer.vue'
import ArchivesToShow from './components/ArchivesToShow.vue'
import PostsToShow from './components/PostsToShow.vue'
import MasonryCard from './components/MasonryCard.vue'

export default {
  name: 'app',
  components: {
    'tab-container': TabContainer,
    'posts-to-show': PostsToShow,
    'archives-to-show': ArchivesToShow,
    'masonry-card': MasonryCard,
  },
  data() {
    return {
      dataPosts: TOPICS,
      dataArchives: ARCHIVES,
      dataPages: PAGES,
      listTabs: TABS,
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
  color: #2c3e50;
  margin-top: 60px;
}
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}
.content {
  margin: 0 auto;
  width: 70%;
  padding: 50px 10px;
}
#app h1 {
  text-align: center;
}
</style>
