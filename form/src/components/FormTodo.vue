<template>
<div class="form-todo form-group">
      <p>
        <input
          placeholder="nome"
          type="text"
          name="author"
          class="form-control"
          v-model="name"
        />
      </p>
      <p>
        <textarea
          placeholder="Comentário"
          name="message"
          class="form-control"
          v-model="message"
        ></textarea>
      </p>
      <button
        v-on:click.prevent="addComment"
        type="submit"
        class="btn btn-primary"
      >
        Comentar
      </button>
</div>
</template>

<script>
export default { 
    data() { 
        return {
          name: '',
          message: ''
        }
      },
    methods: {
        addComment() {
          if (this.message.trim() === '') { // No se agregará aquí el comentario si no hay comentario
            return;
          }
        
        this.$emit("add-todo", {
            name: this.name,
            message: this.message,
        });

          this.name = ''; // Lo que hace aquí es que se queden vacían los campos de nombre y comentario, al darle click en comentar
          this.message = '';
        },
    },
}
</script>