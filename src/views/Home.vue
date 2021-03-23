<template>
  <div class="home">
    <carousel-slider />
  </div>
</template>

<script>
import CarouselSlider from "../components/unique/CarouselSlider";
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      active: 1,
    }
  },
  components: {
    CarouselSlider,
  }
};
</script>
