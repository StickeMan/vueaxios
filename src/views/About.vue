<template>
  <div v-if="result" class="about">
    <h1>This is an about page</h1>
    <p>user ID:{{ result.userId }}</p>
    <p>title: {{ result.title }}</p>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data: () => ({
    result: null,
  }),
  created() {
    let post = {
      tittle: "2005040",
      body: "<p>2005040</p>",
      userID: 1,
    };
    let post_update = {
      tittle: "2005040",
      body: "<p>2005040</p>",
      userID: 1,
    };
    axios.get("https://jsonplaceholder.typicode.com/todos/1").then((result) => {
      this.result = result.data;
      //console.log(result.data);
    });
    axios
      .post("https://jsonplaceholder.typicode.com/posts", post)
      .then((result) => {
        console.log(result);
      });
    axios
      .put("https://jsonplaceholder.typicode.com/posts/1", post_update)
      .then((result) => {
        console.log(result);
      });
  },
};
</script>
