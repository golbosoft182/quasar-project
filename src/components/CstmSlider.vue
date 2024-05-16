<template>
  <div class="slider" @mousedown="handleMouseDown" @mouseup="handleMouseUp">
    <div
      class="item-container"
      :style="{ transform: `translateX(-${currentIndex * itemWidth}px)` }"
    >
      <transition-group name="fade">
        <div
          v-for="(item, index) in jsonData"
          :key="index"
          class="item"
          :class="{ active: index === currentIndex }"
          :style="{ opacity: index === currentIndex ? 0.9 : 1 }"
        >
          <q-btn flat class="cstm-btn-features">
            <q-avatar square size="72px">
              <a :href="item.urlLink">
                <img :src="item.imgSrc" :alt="'Image ' + (index + 1)" />
              </a>
            </q-avatar>
            <div class="title-features">
              <a :href="item.urlLink">{{ item.headline }}</a>
            </div>
          </q-btn>
        </div>
      </transition-group>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      itemWidth: 100, // Adjust according to your item width
      slideInterval: null,
      isMouseDown: false,
      jsonData: [
        {
          imgSrc: "images/comp-ico.svg",
          headline: "해외 마케팅",
          urlLink: "javascript:;",
        },
        {
          imgSrc: "images/img-ico.svg",
          headline: "퍼블리셔",
          urlLink: "javascript:;",
        },
        {
          imgSrc: "images/cube-ico.svg",
          headline: "캐드원(제도사)",
          urlLink: "javascript:;",
        },
        {
          imgSrc: "images/target-ico.svg",
          headline: "해외 세일즈",
          urlLink: "javascript:;",
        },
        {
          imgSrc: "images/phone-ico.svg",
          headline: "해외 CS",
          urlLink: "javascript:;",
        },
        {
          imgSrc: "images/comp-ico.svg",
          headline: "해외 마케팅",
          urlLink: "javascript:;",
        },
        // Add more items as needed
      ],
    };
  },
  mounted() {
    this.startSlideInterval();
  },
  methods: {
    startSlideInterval() {
      this.slideInterval = setInterval(() => {
        this.slideLeft();
      }, 5000);
    },
    slideLeft() {
      if (this.currentIndex < this.jsonData.length - 1) {
        this.currentIndex++;
      } else {
        this.currentIndex = 0;
      }
    },
    handleMouseDown() {
      this.isMouseDown = true;
    },
    handleMouseUp() {
      this.isMouseDown = false;
    },
  },
};
</script>

<style scoped>
.slider {
  white-space: nowrap;
  overflow: hidden;
  position: relative;
  padding: 60px 0 120px;
  animation: fadeIn 500ms ease-in-out;
}
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.item-container {
  display: flex;
  transition: transform 0.5s ease;
}
.item {
  flex: 0 0 auto;
  margin-right: 15px;
  width: 20%;
}
.cstm-btn-features {
  background-color: rgba(255, 255, 255, 0.3);
  color: white;
  border-radius: 12px;
  padding: 5px 15px;
  width: 100%;
}
.cstm-btn-features img {
  margin-right: 15px;
}
</style>
