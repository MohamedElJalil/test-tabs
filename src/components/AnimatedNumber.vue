<template>
  <div class="animated-number">
    <small class="count">{{value}}</small> <small>Posts</small>
  </div>
</template>
<script>
// Component of a number with count animation from zero
export default {
  name: 'AnimatedNumber',
  props: {
    value: {
      type: Number,
      required: true
    },
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
.animated-number{
  display: initial;
  margin-left: 5px;
}
.animated-number small{
  color: #a6a6a6;
  text-transform: uppercase;
  margin-right: 3px;
}
</style>