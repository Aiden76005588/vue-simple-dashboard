<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import apiBoard from "@/api/board";

export default {
  name: "HomeView",
  mounted() {
    apiBoard
      .getArticle(1)
      .then((response) => {
        console.log("getArticles", response);
      })
      .catch((e) => {
        console.log(e);
      });

    apiBoard
      .getArticles(0)
      .then((response) => {
        console.log("getArticles", response);
      })
      .catch((e) => {
        console.log(e);
      });

    apiBoard
      .postArticle("id", "title", "body")
      .then((response) => {
        console.log("postArticles", response);
      })
      .catch((e) => {
        console.log(e);
      });
  },
  components: {
    HelloWorld,
  },
};
</script>
