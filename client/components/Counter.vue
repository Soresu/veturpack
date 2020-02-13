<template>
  <div class="counter-wrapper">
    <div>{{ msg }}</div>
    <div>
      <img src="https://vuejs.org/images/logo.png" width="200" height="200" />
    </div>
    <div class="counter">
      {{ count }}
    </div>
    <button @click="$store.commit('INCREMENT')">Increment</button>
    <button @click="$store.commit('DECREMENT')">Decrement</button>
    <button @click="$store.dispatch('incrementAsync')">Increment Async</button>
  </div>
</template>

<script>
import * as _ from 'lodash';

export default {
  data() {
    return {
      msg: 'Vetur means "Winter" in icelandic.'
    };
  },
  computed: {
    count() {
      // Intellisense NOT working after "this."
      return this.$store.state.count;
    },
    zero() {
      // Intellisense NOT working after this, because "count" returns a property from "this"
      let num = this.$store.state.count;
      return 0;
    }
  },
  methods: {
    hello() {
      // Intellisense working after "this."
      console.log(this.msg);
    }
  },
  // If you comment "props" out, the intellisense will work again in computed
  props: {}
};
</script>

<style lang="scss" scoped>
.counter-wrapper > * {
  margin-bottom: 50px;
}
.counter {
  margin-left: auto;
  margin-right: auto;
  border-radius: 3px;
  width: 200px;
  height: 200px;
  text-align: center;
  line-height: 200px;
  font-size: 5rem;
  background-color: #f0f0f0;
  user-select: none;
}
</style>
