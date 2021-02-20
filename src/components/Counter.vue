<template>
  <div class="counter">
    <v-card>
      <v-card-text class="text-center">
        <span class="display-4">{{ output(counter) }}</span>
        <br />
      </v-card-text>
      <v-card-actions>
        <v-btn icon @click="$emit('substract')"
          ><v-icon>mdi-minus</v-icon></v-btn
        >
        <v-spacer />
        <v-btn icon @click="$emit('add')"><v-icon>mdi-plus</v-icon></v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>

export default {
  props: {
    counter: {
      type: Number,
      default: 0,
      validator: (value) => {
        return value >= 0;
      },
    },
  },
  data: () => ({
    oldVal: 0,
    user: {
      name: "FFF",
      age: 23,
    },
  }),
  watch: {
    output: {
      immediate: true,
      deep: true,
      handler: (val, oldVal) => {
        console.log("value changed: ", val, oldVal);
      },
    },
  },
  methods: {
    add() {
      this.$emit("add");
    },
    substract() {
      this.$emit("substract");
    },
    output() {
      return this.counter + "ETH";
    },
  },
};
</script>

<style></style>
