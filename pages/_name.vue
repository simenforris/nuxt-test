<template>
  <div>
    Hello {{ name }}
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'HelloPage',
  async asyncData({ params }) {
    return { name: params.name }
  }
})
</script>