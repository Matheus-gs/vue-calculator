<template>
  <button
    @click="addDigit"
    class="button"
    :class="{ double, triple, operator }"
  >
    {{ label }}
  </button>
</template>

<script>
export default {
  props: {
    label: {},
    operator: { type: Boolean },
    double: { type: Boolean },
    triple: { type: Boolean },
  },
  methods: {
    addDigit() {
      this.label == "AC"
        ? this.$parent.clearMemory()
        : this.label == "="
        ? this.$parent.setResult()
        : this.operator
        ? this.$parent.setOperation(this.label)
        : this.$parent.setDigit(this.label);
    },
  },
};
</script>

<style>
:root {
  --bg-button: #f0f0f0;
  --border-button: solid 1px #888888;
}

.button {
  height: 60px;
  font-size: 1.2em;
  background: var(--bg-button);
  border: none;
  border-right: var(--border-button);
  border-bottom: var(--border-button);
  border-radius: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  vertical-align: center;
  outline: none;
  transition: all 0.1s ease-in-out;
}

.button:active {
  background: #ccc;
}

.button.double {
  grid-column: span 2;
}

.button.triple {
  grid-column: span 3;
}

.button.operator {
  background: #fa8231;
  color: #fff;
}

.button.operator:active {
  background: #fa8231cc;
}
</style>