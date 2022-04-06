<template>
      <div>
        <button>{{ value }}</button>
      </div>
</template>

<script>
export default {
  name: 'Display-',
  props: {
    value: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.component-button {
  display: inline-flex;
  width: 25%;
  flex: 1 0 auto;
}

.component-button.wide {
  width: 50%;
}

.component-button button {
  background-color: #e0e0e0;
  border: 0;
  font-size: 1.5rem;
  margin: 0 1px 0 0;
  flex: 1 0 auto;
  padding: 0;
}

.component-button:last-child button {
  margin-right: 0;
}

.component-button.orange button {
  background-color: #f5923e;
  color: white;
}
</style>
