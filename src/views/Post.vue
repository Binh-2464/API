<template>
  <div class="post">
    {{ post }}
  </div>
</template>

<script>
import axios from "axios";
export default {
  data: () => ({
    post: null,
  }),
  mounted() {
    this.getPost();
  },
  methods: {
    getPost() {
        const postId = this.$route.params.id;
      axios
        .get("https://jsonplaceholder.typicode.com/posts/"+postId)
        .then((response) => {
          console.log(response.data);
          this.post = response.data;
        });
    },
  },
};
</script>

<style>
</style>