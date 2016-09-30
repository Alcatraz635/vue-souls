
<template>
  <div id="app">

    <hello></hello>
    <span v-bind:id="id">Inspect me</span>
    <p>
      Welcome to your Vue.js app!

    </p>
    <h4>{{ message }}</h4>
    <button  v-on:click='reverseMessage'>Reverse</button><br />
    <input type="text" v-model="message">
    <h4 v-if="!seen">Fuck</h4>
    <ol>
      <li v-for="todo in todos">
        {{todo.text}}
      </li>
    </ol>
  </div>
</template>

<script>
import Hello from './components/Hello'
import Todo from './components/Todo'

export default {
  components: {
    Hello
  },
  data () {
    return {
      'message': 'Hey Ty!',
      'id': 'inspect-me',
      'seen': true,
      'todos': [
        { text: 'Learn JavaScript' },
        { text: 'Learn Vue' },
        { text: 'Build something awesome' }
      ],
      reverseMessage: () => {
        this.message = this.message.split(' ').reverse().join(' ')
      }
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background: black url('./assets/background.jpg') no-repeat fixed center;
  background-size: cover;
}

#app {
  color: white;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

#app ol {
  text-align: left;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
