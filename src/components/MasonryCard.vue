<template>
  <div class="masonry-card">
    <ul class="list-items">
      <li v-for="item in itemList">
        <img v-bind:src="item.urlImage">
        <div class="title">{{item.title}}</div>
      </li>
    </ul>
  </div>
</template>
<script>
// Component show a masonry layout with a title
export default {
  name: 'MasonryCard',
  props: {
    itemList: Array,
  }
}
</script>
<style scoped>
.list-items {
  /* Asign num of columns */
  column-count: 2;
  column-gap: 4px;  
}
.list-items li {
  position: relative;
}
.list-items li img {
  width: 100% !important;
  height: auto !important;
  animation: FadeInImg 1s linear;
  animation-fill-mode: both;
}
.list-items li .title {
  position: absolute;
  bottom: 8%;
  padding: 0px 22px;
  font-size: 21px;
  font-weight: bold;
  color: #fff;
  text-transform: uppercase;
  text-shadow: 2px 2px 5px #000000;
  animation: FadeInImg 1s linear;
  animation-fill-mode: both;
}
@keyframes FadeInImg { 
  0% {
    opacity: 0;
    transform: scale(.1);
  }

  85% {
    opacity: 1;
    transform: scale(1.05);
  }
  100% {
    transform: scale(1);
  }
}
@media only screen and (max-width: 668px) {
    .list-items li .title {
      font-size: 12px;
    }
}
@media only screen and (max-width: 498px) {
    .list-items {
      column-count: 1;
    }
    .list-items li .title {
      font-size: 15px;
    }
}
</style>