<template>
  <div>
      <p>{{count}}</p>
      <button @click="() => setCount(count - 1)">
        -1
      </button>
      <button @click="() => setCount(count + 1)">
        +1
      </button>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'Counter',
  props: {
    start: {
      type: Number,
      required: false,
      default: 0,
    }
  },
  data() {
    return {
      count: this.start
    }
  }
})
</script>