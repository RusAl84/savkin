<template>
  <div>
    <h1>{{ text }}</h1>
    <form>
      <input v-model="text">
      <button @click="onSendClick">
        нажми меня
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => ({
    text: '',
  }),
  methods: {
    // Реакция на кнопку отправки
    async onSendClick() {
      this.text = this.text + "s"
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
