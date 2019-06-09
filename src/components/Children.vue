<template>
  <div>这是{{test}}</div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component
export default class Children extends Vue {
  @Prop() test: String;
}
</script>

<style lang="">
</style>
