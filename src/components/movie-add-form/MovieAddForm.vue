<template>
  <div class="movie-add-form">
    <h1>Yangi kino qo'shish</h1>
    <form @submit.prevent="addMovie" class="add-form d-flex">
      <input type="text" class="form-control new-movie-label" placeholder="Qanday kino ?" v-model="name" required="true">
      <input type="number" class="form-control new-movie-label" placeholder="Necha marta ko'rilgan?" v-model="viewers" required="true">
      <button class="btn btn-outline-dark" type="submit">Qo'shish</button>
    </form>
  </div>
</template>

<script>
export default{
  data() {
    return {
      name: "",
      viewers: "",
    }
  },
  methods: {
    addMovie() {
      const newMovie = {
        name: this.name,
        viewers: this.viewers,
        favourite: false,
        like: false,
        id:Date.now()
      }
      this.$emit('createMovie',newMovie)
      this.name = '',
      this.viewers = ''
    }
  }
}
</script>

<style>
  .movie-add-form {
    margin-top: 2rem;
    padding: 1.5rem;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
  }
</style>
