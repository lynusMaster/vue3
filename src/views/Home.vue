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
import apiBoard from '@/api/board';

export default {
  mounted() {
    apiBoard.getArticle(1)
      .then(function (response) {
        console.log("getArtcle", response);
        console.log("getArtcle.data", response.data);
      })
      .catch(function (e) {
        console.log(e);
      });
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
</style>