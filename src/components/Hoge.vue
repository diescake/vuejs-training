<template>
  <div id="hoge">
    <h1>{{ msg }}</h1>
    <a :href="href">link</a>
    <br>
    <ul>
      <li :key="todo.text" v-for="todo in todos"> {{ todo.text }}</li>
    </ul>
    <button @click="increment">+</button> / <button @click="decrement">-</button>
    <p>{{ total }}</p>
    <p v-once>{{ total }}</p>
    <span v-if="total > 0" :title="msg">larger</span>
    <span v-else-if="total === 0" :title="msg">same</span>
    <span v-else>smaller</span>
  </div>
</template>

<script>
export default {
  name: 'Hoge',
  data: () => ({
    msg: 'Welcome to Your Hoge App',
    href: 'https://www.google.com',
    total: 0,
    todos: [
      { text: '食う' },
      { text: '寝る' },
      { text: '遊ぶ' },
    ],
  }),
  methods: {
    increment() {
      this.total += 1;
      this.msg = 'incremented';
    },
    decrement() {
      this.total -= 1;
      this.msg = 'decremented';
    },
  },
};
</script>

<style scoped>
p {
  color: red;
}
</style>
