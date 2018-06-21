<template>
  <div class="tabs">
    <div class="tabs-header">
      <ul>
        <li v-for="tab in tabs" @click="(e) => activeTab = tab" :class="activeTab === tab ? 'active' : ''">
          {{ tab }}
        </li>
      </ul>
    </div>
    <div class="tabs-content">
      <slot :name="tab" v-for="tab in tabs" v-if="tab === activeTab" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'TabContainer',
  props: {
    tabs: Array,
  },
  data() {
    return {
      activeTab: this.tabs[Math.floor((Math.random() * 3))],
    };
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.tabs {
  margin-bottom: 10px;
  max-width: 600px;
}

.tabs-header ul {
  position: relative;
  padding: 0;
  margin: 0 auto;
  text-align: left;
}
.tabs-header ul:before {
  z-index: 1;
}
.tabs-header ul:after {
  position: absolute;
  content: "";
  width: 100%;
  bottom: 0;
  left: 0;
  border-bottom: 1px solid;
  z-index: 1;
}

.tabs-header ul li {
  text-transform: uppercase;
  font-size: 13px;
  font-weight: 600;
  margin-right: 4px;
  padding: 6px 16px;
  border: 1px solid #484c56;
  color: #e5c491;
  cursor: pointer;
  background: #484c56;
  display: inline-block;
  z-index: 0;
  position: relative;
  box-shadow: inset 0px -33px 28px -12px rgba(55,59,69,1);
  text-align: center;
}
.tabs-header ul li.active {
  background-color: #ffffff;
  z-index: 2;
  border-bottom-color: #FFF;
  color: #484c56;
  box-shadow: none;
  max-height: auto;
}
.tabs-content {
  padding: 35px 30px;
  border-bottom: 1px solid;
  border-right: 1px solid;
  border-left: 1px solid;
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

@media only screen and (max-width: 498px) {
    .tabs-header ul li {
      font-size: 10px;
      margin: 0;
    }
}
@media only screen and (max-width: 350px) {
    .tabs-header ul li {
      font-size: 8px;
    }
}
</style>
