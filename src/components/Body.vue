<template>
  <div class="body main">
    <div class="cstm-container">
      <div class="inner-container">
        <div class="row">
          <div class="col-12 col-md-7">
            <CstmAnimation />
          </div>
          <div class="col-12 col-md-5">
            <CstmCarousel />
          </div>
        </div>
      </div>
    </div>
    <CstmSlider />
  </div>
</template>

<script>
import CstmAnimation from "./Animation.vue";
import CstmCarousel from "./CstmCarousel.vue";
import CstmSlider from "./CstmSlider.vue";

export default {
  name: "CstmBody",
  components: {
    CstmAnimation,
    CstmCarousel,
    CstmSlider,
  },
};
</script>

<style scoped>
.body {
}
</style>
