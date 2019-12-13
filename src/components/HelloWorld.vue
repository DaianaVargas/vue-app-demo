<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['msg'],
};
</script>

<style scoped>
h1 {
  font-size: 28px;
  font-weight: bold;
}
</style>
