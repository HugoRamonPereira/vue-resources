<template>
  <button :class='mode'>
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['mode']
}
</script>

<style scoped>
button {
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  background-color: #3a0061;
  border: 1px solid #3a0061;
  color: white;
  cursor: pointer;
  border-radius: 8px;
}

button:hover,
button:active {
  background-color: #270041;
  border-color: #270041;
  transition: all .2s;
}

.flat {
  background-color: transparent;
  color: #3a0061;
  border: none;
  border-radius: 8px;
}

.flat:hover,
.flat:active {
  background-color: #edd2ff;
  transition: all .2s;
}

.ghost {
  background-color: #dfccd6;
  color: #3a0061;
  border: none;
  border-radius: 8px;
}

.ghost:hover,
.ghost:active {
  background-color: #d0b2c1;
  transition: all .2s;
}
</style>