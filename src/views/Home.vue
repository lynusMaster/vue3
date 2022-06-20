<template>
  <div>
    <h1>Home</h1>
    <div class="link-block">
        <router-link to="/">Home</router-link>
        <router-link to="/test">Test</router-link>
    </div>
  </div>
</template>
<script>
export default {

}
</script>
<style lang="scss" scoped>
.link-block {
    a {
        display: inline-block;
        margin: 0 5px;
    }
}
</style>