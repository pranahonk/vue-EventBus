<template>
  <div id="app">
    <Value/>
    <ChangeValue/>
  </div>
</template>

<script>
import Value from './components/Value.vue'
import ChangeValue from './components/ChangeValue.vue'
export default {
  name: 'app',
  components: {
    Value,
    ChangeValue
  }
}
</script>