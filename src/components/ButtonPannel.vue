<template>
    <div class="component-button-panel">
        <div>
          <Button name="AC" @click="handleClick" />
          <Button name="+/-" @click="handleClick" />
          <Button name="%" @click="handleClick" />
          <Button name="÷" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="7" @click="handleClick" />
          <Button name="8" @click="handleClick" />
          <Button name="9" @click="handleClick" />
          <Button name="x" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="4" @click="handleClick" />
          <Button name="5" @click="handleClick" />
          <Button name="6" @click="handleClick" />
          <Button name="-" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="1" @click="handleClick" />
          <Button name="2" @click="handleClick" />
          <Button name="3" @click="handleClick" />
          <Button name="+" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="0" @click="handleClick" isWide />
          <Button name="." @click="handleClick" />
          <Button name="=" @click="handleClick" isOrange />
        </div>
      </div>
</template>

<script>

import Button from './Button.vue';

export default {
  components: { Button },
  name: 'Display-',
  props: {
    clickHandler: Function,
  },

  methods: {
    handleClick(buttonName) {
      console.log(buttonName);
      alert('jj');
      this.props.clickHandler(buttonName);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.component-display {
  background-color: #858694;
  color: white;
  text-align: right;
  font-weight: 200;
  flex: 0 0 auto;
  width: 100%;
}

.component-display > div {
  font-size: 2.5rem;
  padding: 0.2rem 0.7rem 0.1rem 0.5rem;
}
</style>
