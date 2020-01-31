<template>
  <div>
    <button @click="addValue">Add Value</button>
    <button @click="minValue">Minus Value</button>
    <button @click="resetValue">Reset Value</button>
    <div>{{value}}</div>
  </div>
</template>

<script>
import { EventBus } from "@/main.js";
export default {
  data() {
    return {
      value: 0
    };
  },
  methods: {
    addValue() {
      this.value++;
      EventBus.$emit("changeValue", this.value);
    },
    minValue() {
      this.value--;
      EventBus.$emit("minValue", this.value);
    },
    resetValue() {
      this.value = 0;
      EventBus.$emit("restValue", this.value);
    }
  },
  created() {
    EventBus.$on("timesTwo", val => {
      this.value = val;
    });
  }
};
</script>