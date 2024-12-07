<template>
    <div :style="{ backgroundColor: color }" class="bookContainer">
        <img :src="book.comicImage" alt={{book.comicBook_title}} />
        <h3>{{ book.comicBook_title }}</h3>
        <p>{{book.comicBook_author}}</p>
        <p>{{book.comicBook_genre}}</p>
        <p> $ {{book.comicBook_price}}</p>
        <p>{{book.comicBook_releaseDate}}</p>
    </div>  
</template>

<script>
    export default{
        name:"ComicBook",
        props:{
            book: Object,
            color: String,
        }
    }
</script>

<style scoped>
.bookContainer{
    width:200px;
    margin: 1em auto;
    padding:1em;
    text-align:center;
    border:transparent;
    border-radius: 4px;
    padding: 10px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    font-size: 20px;
}

.bookContainer img{
    width:180px;
    height:300px;
}
    
</style>