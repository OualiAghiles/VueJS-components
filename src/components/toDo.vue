<template lang="html">
  <div>
    <h3 class="ui header">Todos</h3>
    <div class="ui segments">
      <div class="ui blue segment">
        <div class="ui form">
          <div class="field">
            <input name="first-name" placeholder="Ajouter votre tâche" type="text" v-model="newTodo" @keyup.enter.prevent="addTodo">
          </div>
        </div>
      </div>
      <div class="ui segment" v-for="todo in todos" :key="todo.id">
        <div class="ui toggle checkbox">
          <input name="public" type="checkbox">
          <label>
            <h3> {{ todo.name }}
              <a href="#" @click.prevent="collapse" v-show="todo.description"><i class="caret down icon"></i></a>
            </h3>
            <div class="ui fitted divider" v-show="collapsed"></div>
            <p v-show="collapsed"> {{todo.description}} </p>
          </label>
        </div>
      </div>
      <div class="ui secondary segment">
        <div class="ui tree top attached buttons">
          <div class="ui button">One</div>
          <div class="ui button">Two</div>
          <div class="ui button">Three</div>
        </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      todos: [{
        name: 'Tache de test',
        description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Facilis, nostrum.',
        completed: false
      }],
      newTodo: '',
      collapsed: false
    }
  },
  methods: {
    addTodo () {
      this.todos.push({
        completed: false,
        name: this.newTodo
      })
      this.newTodo = ''
    },
    collapse () {
      this.collapsed = !this.collapsed
    }
  }
}
</script>

<style lang="css">
</style>
