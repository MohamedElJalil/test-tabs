<template>
  <div class="archives-to-show">
    <ul class="list-archives">
      <li v-for="archive in listOfArchives">
        <img v-bind:src="archive.urlImage">
        <div class="description">{{archive.description}}</div>
      </li>
    </ul>
  </div>
</template>
<script>
// Component that show a list with image and text
export default {
  name: 'ArchivesToShow',
  props: {
    listOfArchives: Array,
  },
  mounted: () => {
    /**
     * Method to generate an animation to count from zero
     */
    $('.count').each(function () {
      $(this).prop('Counter',0).animate({
        Counter: $(this).text()
      }, {
        duration: 1000,
        easing: 'swing',
        step: function (now) {
          // Display numbers
          $(this).text(Math.ceil(now));
        }
      });
    });
  }

}
</script>
<style scoped>
.archives-to-show li {
  margin-bottom: 15px;
  display: inline-block;
	vertical-align: top;
}
.archives-to-show li:last-child {
  margin-bottom: 0px;
}
.archives-to-show img {
  max-width: 80px;
  margin-right: 10px;
  float: left;
	width: 100%;
  border-radius: 40px;
  box-shadow: 14px 18px 80px -27px rgba(0,0,0,0.75);
  animation: FadeInImg 1s linear;
  animation-fill-mode: both;
}
.archives-to-show .description {
  margin-top: 10px;
  position: relative;
  animation: LinealDescription 1s linear;
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
@keyframes LinealDescription { 
  0% {
    opacity: 0;
  }

  50% {
    opacity: 0;
    transform: scale(1.05);
    left: 40%;
  }
  100% {
    opacity: 1;
    transform: scale(1);
    left: 0%;
  }
}
</style>