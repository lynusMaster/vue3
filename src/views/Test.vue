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
  </div>
</template>
<script>
import { computed } from "vue";
import { useStore } from "vuex";
export default {
  setup() {
    const store = useStore();
    const counter = computed(() => store.state.counter);
    const test = computed(() => store.getters);
    const inc = () => store.commit("setCounter", counter.value + 1);

    return { counter, inc, test };
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
        cursor: pointer;
    }
}
</style>