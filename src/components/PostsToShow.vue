<template>
  <div class="posts-to-show">
    <ul class="list-posts">
      <li v-for="post in listOfPosts">{{post.name}} <animated-number :value="post.numPosts"></animated-number></li>
    </ul>
  </div>
</template>
<script>
import AnimatedNumber from './AnimatedNumber.vue'
// Component to show a list of posts
export default {
  name: 'PostsToShow',
  props: {
    listOfPosts: Array,
  },
  components: {
    'animated-number': AnimatedNumber
  }
}
</script>
<style scoped>
.list-posts li:first-child{
  padding-top: 0;
}
.list-posts li{
  padding: 15px 0;
  border-bottom: 1px solid #a6a6a6;
  position: relative;
}
.list-posts li:last-child{
  border-bottom: none;
  padding-bottom: 0;
}
</style>