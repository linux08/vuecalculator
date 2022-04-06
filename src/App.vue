<template>
  <div class="component-app">
    <Display
      :value="0"
     />
    <ButtonPanel :clickHandler="handleClick" />
  </div>
</template>

<script>
import Display from './components/Display.vue';
import ButtonPanel from './components/ButtonPannel.vue';
import calculate from './logic/calculate';

export default {
  components: { Display, ButtonPanel },
  name: 'App',
  data() {
    return {
      total: null,
      next: null,
      operation: null,
    };
  },
  methods: {
    handleClick(event) {
      console.log('djdh', event);
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

<style>
.component-app {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  height: 100%;
}
</style>
