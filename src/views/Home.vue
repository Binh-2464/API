<template>
  <div class="Home">
    <v-row justify="center">
      <v-col cols="4">
        <counter :counter="counter" @add="counter += 1" @substract="counter -= 1"/>
      </v-col>
      <v-col cols="12">
          <v-col  v-for="(post , index) in posts" :key="`post-${index}`">
            <v-card :to="`/Posts/${post.id}`">
              <v-card-title>{{post.id}} {{post.title}}</v-card-title>
            </v-card>
          </v-col>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import axios from 'axios'
import Counter from '@/components/Counter.vue'
export default {
  components: { Counter },
  data: () => ({
    posts: [],
    Counter : 0
  }),  
  mounted(){
    this.getPost();
  },
  methods:{
    getPost(){
      // fetch('https://jsonplaceholder.typicode.com/posts').then(respone => {
      //   console.log(respone.body);
      // });
      axios.get('https://jsonplaceholder.typicode.com/posts').then(respone =>{
        console.log(respone);
        this.posts = respone.data;
      })
      }
  }
}
</script>

<style>

</style>