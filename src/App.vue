<template>
<div> 
    <app-nav></app-nav>
    <app-slider></app-slider>
</div>
</template>

<script>
import Nav from './components/Nav.vue';
import Slider from './components/Slider.vue';
export default {
  components: {
    'app-nav': Nav,
    'app-slider': Slider
  },
  data() {
    return {

    };
  }
}
</script>
