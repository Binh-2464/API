<template>
  <div class="Home">
    <v-row justify="center">
      <v-col cols="4">
        <counter :counter="counter" @add="counter += 1" @substract="counter -= 1"/>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import Counter from '@/components/Counter.vue'
export default {
  components: { Counter },
  data: () => ({
    counter: -1,
  }),  
}
</script>

<style>

</style>