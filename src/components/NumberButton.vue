<template>
  <button @click="click" class="number-button">
    {{ number }}
  </button>
</template>

<script>
export default {
  name: 'NumberButton',
  props: {
    number: {
      type: String,
      required: true
    }
  },
  data () {
    return {
    }
  }, 
  methods : {
    click () {
      this.$emit('click', this.number)
    }
  } 
};
</script>
<style lang="scss" scoped>
.number-button {
  cursor: pointer;
  flex: 1;
  border: 1px solid #3C3C3C;
  width: 100%;
  font-size: 1.2rem;
  padding: 0.6rem 0;
  text-align: center;
  background-color: #6A6A6A;
  color: #E0E0E0;
}
</style>
