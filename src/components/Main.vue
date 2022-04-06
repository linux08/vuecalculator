<template>
  <div class="component-app">
    <Display
      :value="0"
     />
    <ButtonPanel :clickHandler="handleClick" />
  </div>
</template>

<script>

import Display from './Display.vue';
import ButtonPanel from './ButtonPannel.vue';
import calculate from '../logic/calculate';

export default {
  components: { Display, ButtonPanel },
  name: 'HelloWorld',
  data() {
    return {
      total: null,
      next: null,
      operation: null,
    };
  },
  methods: {
    handleClick(event) {
      console.log(event.target.name);
      this.data = (calculate(this.data, event));
    },
  },
  computed: {
    displayValue() {
      return this.next || this.total || '0';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .component-app {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    height: 100%;
  }
</style>
