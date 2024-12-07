<template>
  <div class="catalogGrid">
    <div
      v-for="(book, index) of bookList"
      :key="book.comicBook_title"
      class="gridItem"
    >
      <!-- Send color by matching index -->
      <ComicBook :book="book" :color="colors[index % colors.length]" />
    </div>
  </div>
</template>

<script>
import ComicBook from "./ComicBook.vue";

export default {
  name: "ComicBookCatalog",
  components: {
    ComicBook,
  },
  props: {
    bookList: Array,
  },
  data() {
    return {
      colors: ["#ff746c", "#4781cb", "#8e6903", "#49636c", "#f4c445"],
    };
  },
};
</script>

<style scoped>
.catalogGrid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 20px;
  padding: 20px;
  background-color: rgb(25, 26, 26);
}

.gridItem {
  display: grid;
  justify-content: center;
}
</style>
