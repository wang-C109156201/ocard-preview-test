<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>{{ propData }}</div>
</template>

<script lang="ts">

export default {
  props: {
    propData: {
      type: String,
      default: '我是默认值'
    }
  }
}
</script>

<style scope>

</style>