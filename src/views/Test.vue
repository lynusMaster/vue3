<template>
  <div>
    <h1>Test</h1>
    <div class="link-block">
        <router-link to="/">Home</router-link>
        <router-link to="/test">Test</router-link>
    </div>
    <div class="btn-block">
        {{ counter }}
        <button @click="inc">inc</button>
    </div>
    <div class="swiper-block">
        <swiper
        :slides-per-view="1"
        :space-between="50"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
        >
            <swiper-slide>Slide 1</swiper-slide>
            <swiper-slide>Slide 2</swiper-slide>
            <swiper-slide>Slide 3</swiper-slide>
        </swiper>
    </div>
  </div>
</template>
<script>
// import SwiperClass, { Pagination } from 'swiper'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'

// import swiper module styles
import 'swiper/css'
// import 'swiper/css/pagination'
// more module style...


import { computed } from "vue";
import { useStore } from "vuex";
export default {
    components: {
      Swiper,
      SwiperSlide
    },
  setup() {
    
    const store = useStore();
    const counter = computed(() => store.state.counter);
    const test = computed(() => store.getters);
    const inc = () => store.commit("setCounter", counter.value + 1);

    const onSwiper = (swiper) => {
        console.log(swiper);
    };
    const onSlideChange = () => {
        console.log('slide change');
    };

    return { 
        counter,
        test,
        inc,
        onSwiper,
        onSlideChange,
    };
  }
}
</script>
<style lang="scss" scoped>
.link-block {
    a {
        display: inline-block;
        margin: 0 5px;
    }
}
.btn-block {
    button {
        outline: 0;
        border: 0;
        background-color: yellowgreen;
        color: white;
        cursor: pointer;
    }
}
</style>