<template>
  <div class="container">
    <h1>Comentários</h1>
    <hr />
    <FormTodo v-on:add-todo="add" />
    <div class="list-group">
    <p v-if="comments.length <=0">Sin comentarios...</p>
      <div class="list-group-item" v-for="(comment, index) in allComments" :key="index">
        <span class="comment__author"
          >Autor: <strong>{{ comment.name }}</strong></span
        >
        <p>{{ comment.message }}</p>
        <div>
          <a href="#" title="Excluir" v-on:click.prevent="removeComment(index)"
            >Excluir</a
          >
        </div>
      </div>
    </div>
    <hr />
  </div>
</template>

<script>
import FormTodo from "./FormTodo"
export default {
    components: {
      FormTodo
    },
    data() { // Cuando lo mande para la base de datos, el nombre y el autor se quedará con la string vacía. Lo que se manda a la base de datos es esto, y no lo que está dentro del computed
        return {
          comments: [],
        }
      },
      methods: {
        add(comment) {
          this.comments.push(comment);
        },
        removeComment(index) {
          // Para borrar es muy fácil, pero necesito saber en qué posición debo borrar, así que utilizaré del index
          this.comments.splice(index, 1)
        }
      },
      computed: { // está más relacionado con la parte de visualización, con lo que quieres enseñar. Eso es solo para customizar lo que va para la el template, evitando poner lógica dentro de él
        allComments() {
          return this.comments.map(comment => ({
            ...comment, name: comment.name.trim() === '' ? "Anonimo" : comment.name
          }))
        }
      }
}
</script>
