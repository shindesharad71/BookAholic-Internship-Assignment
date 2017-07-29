<template>
<div> 
    <app-nav></app-nav>
    <app-slider></app-slider>
    <app-products></app-products>
</div>
</template>

<script>
import Nav from './components/Nav.vue';
import Slider from './components/Slider.vue';
import Products from './components/Products.vue';
export default {
  components: {
    'app-nav': Nav,
    'app-slider': Slider,
    'app-products': Products
  },
  data() {
    return {

    };
  }
}
</script>
