<template>
  <div
    class="slider desktop-only"
    @mousedown="handleMouseDown"
    @mouseup="handleMouseUp"
  >
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
  <div class="checklist-cstm mobile-only">
    <div class="q-pa-md">
      <div class="q-gutter-sm">
        <q-checkbox v-model="teal" label="한국어 능력" color="white" />
        <q-checkbox v-model="teal" label="업무 수행 능력" color="white" />
      </div>
      <div class="q-gutter-sm">
        <q-checkbox v-model="teal" label="겸업 여부" color="white" />
        <q-checkbox v-model="teal" label="평판 조회" color="white" />
      </div>
      <div class="q-gutter-sm link-slider-cstm">
        <p>
          <a href="javascript:;">개발자가 필요하신가요?</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  data() {
    return {
      teal: ref(true),
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
.checklist-cstm {
  font-size: 16px;
  font-weight: 900;
  color: #ffffff;
}
.q-checkbox__svg {
  color: #2c599b !important;
}
.link-slider-cstm {
  margin: 10px 0 30px;
}
.link-slider-cstm,
.link-slider-cstm a {
  color: #fbff23;
  font-size: 16px;
}
</style>
