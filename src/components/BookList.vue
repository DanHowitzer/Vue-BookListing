<template>
  <div class="BookList">
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" :book="book"></book-item>
    </ul>
    <book-form v-on:addBook="appendBook"></book-form>
  </div>
</template>

<script>
    import BookItem from "./BookItem"
    import BookForm from "./BookForm"
    export default {
        name: "BookList",
        components: {
          BookItem,
          BookForm
        },
        methods: {
          appendBook(bookTitle, bookAuthor) {
            this.books.push({ title: bookTitle, author: bookAuthor })
          }
        },
        data () {
          return {
            title: 'All Books',
            books: [
              {title: 'Self-Reliance', author: 'Raph Waldo Emerson'},
              {title: 'American Gods', author: 'Neil Gaiman'},
              {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
            ]
          }
        }
    }
</script>

<style scoped>
h1, h2 {
  font-weight:normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
