<template>
    <div>
        <button v-on:click="changeCounter">
            Você clicou em mim {{ counter }} vezes.
        </button>
    </div>
</template>

<script>
export default {
  name: 'ButtonCounter',
  data() {
    return {
      count: 0,
    };
  },
  props: ['counter', 'changeCounter'],
  methods: {
    alertCounter() {
      this.count += 1;
    },
  },
};
</script>

<style scoped>
button {
  border: none;
  padding: 16px;
  border-radius: 6px;
  cursor: pointer;
  background: #fccf08;
  color: rgb(0, 0, 0);
  font-size: 20px;
  font-weight: bold;
  margin-top: 30px;
}
</style>
