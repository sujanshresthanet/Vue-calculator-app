<template>
  <div id="app" class="container">
    <h1 class="title">Vue.js Calculator</h1>
    <div class="calculator">
      
      <!-- Input and Result Display Combined -->
      <div class="display">
        <input v-model="input" type="text" readonly />
        <p v-if="result">{{ result }}</p>
      </div>

      <!-- Buttons -->
      <div class="buttons">
        <button @click="clear" class="btn-clear">C</button>
        <button @click="deleteLast" class="btn-delete">DEL</button>
        <button @click="append('/')" class="btn-operator division">/</button>
        <button @click="append('*')" class="btn-operator multiplication">*</button>

        <button @click="append('7')">7</button>
        <button @click="append('8')">8</button>
        <button @click="append('9')">9</button>
        <button @click="append('-')" class="btn-operator subtraction">-</button>

        <button @click="append('4')">4</button>
        <button @click="append('5')">5</button>
        <button @click="append('6')">6</button>
        <button @click="append('+')" class="btn-operator addition">+</button>

        <button @click="append('1')">1</button>
        <button @click="append('2')">2</button>
        <button @click="append('3')">3</button>
        <button @click="calculate" class="btn-equal">=</button>

        <button @click="append('0')" class="span-two">0</button>
        <button @click="append('.')">.</button>

        <!-- Trigonometric Functions -->
        <button @click="trig('sin')" class="btn-trig">sin</button>
        <button @click="trig('cos')" class="btn-trig">cos</button>
        <button @click="trig('tan')" class="btn-trig">tan</button>

        <!-- Additional Math Operations -->
        <button @click="sqrt" class="btn-operator square-root">√</button>
        <button @click="pow" class="btn-operator power">x²</button>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: "",
      result: ""
    };
  },
  methods: {
    append(character) {
      this.input += character;
    },
    clear() {
      this.input = "";
      this.result = "";
    },
    deleteLast() {
      this.input = this.input.slice(0, -1);
    },
    calculate() {
      try {
        this.result = eval(this.input).toString();
      } catch {
        this.result = "Error";
      }
    },
    trig(func) {
      try {
        if (func === "sin") {
          this.result = Math.sin(this.toRadians(parseFloat(this.input))).toString();
        } else if (func === "cos") {
          this.result = Math.cos(this.toRadians(parseFloat(this.input))).toString();
        } else if (func === "tan") {
          this.result = Math.tan(this.toRadians(parseFloat(this.input))).toString();
        }
      } catch {
        this.result = "Error";
      }
    },
    sqrt() {
      try {
        this.result = Math.sqrt(parseFloat(this.input)).toString();
      } catch {
        this.result = "Error";
      }
    },
    pow() {
      try {
        this.result = Math.pow(parseFloat(this.input), 2).toString();
      } catch {
        this.result = "Error";
      }
    },
    toRadians(degrees) {
      return (degrees * Math.PI) / 180;
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  min-height: 100vh;
  padding: 20px;
}

.title {
  font-size: 2em;
  margin-bottom: 20px;
  text-align: center;
}

.calculator {
  width: 100%;
  max-width: 400px;
  background: #f8f9fa;
  border-radius: 10px;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  padding: 20px;
}

.display {
  width: 95%;
  margin-bottom: 10px;
  background: #333;
  color: white;
  border-radius: 5px;
  padding: 10px;
}

.display input {
  width: 100%;
  height: 50px;
  font-size: 1.5em;
  background: transparent;
  color: white;
  border: none;
  text-align: right;
}

.display p {
  font-size: 1.2em;
  margin: 5px 0 0;
  text-align: right;
}

.buttons {
  display: flex;
  flex-wrap: wrap;
}

.buttons button {
  flex: 1 1 22%;
  margin: 5px;
  padding: 15px;
  font-size: 1.2em;
  background-color: #007bff; /* Default blue background */
  color: white; /* White text for visibility */
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.btn-operator {
  background-color: #6f42c1; /* Purple for operator buttons */
}

.btn-operator.division {
  background-color: #dc3545; /* Red for division */
}

.btn-operator.multiplication {
  background-color: #28a745; /* Green for multiplication */
}

.btn-operator.subtraction {
  background-color: #ffc107; /* Yellow for subtraction */
}

.btn-operator.addition {
  background-color: #17a2b8; /* Cyan for addition */
}

.btn-operator.square-root {
  background-color: #6c757d; /* Gray for square root */
}

.btn-operator.power {
  background-color: #fd7e14; /* Orange for power */
}

.btn-trig {
  background-color: #ff5733; /* Different color for trigonometric functions */
}

.btn-equal {
  background-color: #007bff; /* Blue for equals button */
}

.btn-clear {
  background-color: #17a2b8; /* Cyan for clear button */
}

.btn-delete {
  background-color: #6c757d; /* Gray for delete button */
}

.buttons button:hover {
  opacity: 0.9;
}

.buttons .span-two {
  flex: 1 1 48%;
}

@media (max-width: 600px) {
  .buttons button {
    font-size: 1em;
    padding: 12px;
  }

  .display, .display p {
    font-size: 1.2em;
  }
}
</style>
