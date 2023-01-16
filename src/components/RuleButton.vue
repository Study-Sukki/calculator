<template>
  <button
    class="rule-button"
    :class="{ 'complex': isComplex }"
  >
    {{ rule }}
  </button>
</template>

<script>
export default {
  name: 'RuleButton',
  props: {
    rule: {
      type: String,
      required: true,
    },
    isComplex: {
      type: Boolean,
      required: false,
      default: false,
    }
  },
  data () {
    return {


    }
  },
  methods: function () {

  },
};
</script>
<style lang="scss" scoped>

.rule-button {
  cursor: pointer;
  flex: 1;
  border: 1px solid #3C3C3C;
  width: 100%;
  font-size: 1.2rem;
  padding: 0.6rem 0;
  text-align: center;
  background-color: #FD8E0E;
  color:  #E0E0E0;
}
.complex {
  background-color: #4E4E4E;
}
</style>
