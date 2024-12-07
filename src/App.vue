<template>
  <ComicBookHeader/>
  <ComicBookCatalog :bookList = bookList />
</template>

<script>
  import ComicBookHeader from "./components/ComicBookHeader.vue";
  import ComicBookCatalog  from "./components/ComicBookCatalog.vue";

  export default{
    name: "App",
    components:{
      ComicBookHeader,
      ComicBookCatalog 
    },
    data(){
      return{
        bookList:[]
      }
    },
    methods:{
      async fetchBooksList(){
        const res = await fetch("https://comic-book-details.onrender.com/api");
        const bookData = await res.json();
        return bookData[0].comicBooks;
      }
    },
    async created(){
        this.bookList = await this.fetchBooksList();
    }
  }
</script>

<style scoped>
</style>