<template>
  <div class="hello">
    <h1> This is a child getting data from parent via injector.</h1>
    {{childMessage}}
  </div>
</template>

<script>
export default {
  name: 'ChildInjector',
  inject: ['childMessage'],
}
</script>

<style>
</style>
