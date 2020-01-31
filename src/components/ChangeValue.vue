<template>
  <div>
    <div>{{ datvalue }}</div>
    <button @click="timesTwo">Times Two</button>
  </div>
</template>

<script>
import { EventBus } from "@/main.js";
export default {
  data() {
    return {
      datvalue: 0
    };
  },
  methods: {
    timesTwo() {
      this.datvalue = this.datvalue * 2;
      EventBus.$emit("timesTwo", this.datvalue);
    }
  },
  created() {
    EventBus.$on("changeValue", val => {
      this.datvalue = val;
    });
    EventBus.$on("minValue", val => {
      this.datvalue = val;
    });
    EventBus.$on("restValue", val => {
      this.datvalue = val;
    });
  }
};
</script>