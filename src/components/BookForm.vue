<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
      <div>
        <label for="finishedReading">
          Finished Reading
          <input v-model="bookData.finishedReading" type="checkbox" name="finishedReading" value="">
        </label>
      </div>
    </div>
    <div>
      <label for="borrowed">
        borrowed
        <input v-model="bookData.ownership" type="radio" id="borrowed" value="borrowed">
      </label>
      <label for="bought">
        bought
        <input v-model="bookData.ownership" type="radio" id="bought" value="bought">
      </label>
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
