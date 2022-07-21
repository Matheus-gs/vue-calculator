<template>
  <div class="calculator">
    <CalculatorDisplay :displayValue="result ?? 0" />
    <CalculatorButton label="AC" />
    <CalculatorButton label="+/-" operator />
    <CalculatorButton label="%" operator />
    <CalculatorButton label="/" operator />
    <CalculatorButton label="7" />
    <CalculatorButton label="8" />
    <CalculatorButton label="9" />
    <CalculatorButton label="*" operator />
    <CalculatorButton label="4" />
    <CalculatorButton label="5" />
    <CalculatorButton label="6" />
    <CalculatorButton label="-" operator />
    <CalculatorButton label="1" />
    <CalculatorButton label="2" />
    <CalculatorButton label="3" />
    <CalculatorButton label="+" operator />
    <CalculatorButton label="0" double />
    <CalculatorButton label="," />
    <CalculatorButton label="=" operator />
  </div>
</template>

<script>
import CalculatorDisplay from "../components/CalculatorDisplay";
import CalculatorButton from "../components/CalculatorButton";

export default {
  components: {
    CalculatorButton,
    CalculatorDisplay,
  },

  data() {
    return {
      operation: [],
      result: null,
    };
  },

  methods: {
    clearMemory() {
      console.log("Memória limpa");
      this.operation = [];
      this.result = null;
    },

    setDigit(digit) {
      console.log(`Digito: ${digit}`);
      this.operation.push(digit);
      this.result == null ? (this.result = digit) : (this.result += digit);
    },

    setOperation(operator) {
      console.log(`Operação: ${operator}`);
      this.operation.push(operator);
      this.result += operator;
    },

    setResult() {
      let calc = this.operation.toString().replaceAll(",", " ");
      this.result = this.getResult(calc);
    },

    getResult(calc) {
      let result = eval(calc);

      if (result !== 0) {
        this.operation = [];
        this.operation.push(result);
        return result;
      } else {
        this.clearMemory();
      }
    },
  },
};
</script>

<style>
.calculator {
  width: 235px;
  height: 320px;

  border-radius: 5px;

  display: grid;
  grid-template-columns: repeat(4, 25%);
  grid-template-rows: 1fr repeat(48px, 5);

  gap: 0.2em;
}
</style>