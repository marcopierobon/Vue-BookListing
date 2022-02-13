<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <book-item v-for="book in books" :book="book" :key="book.title" />
            <book-form @addBook='appendBook' />
        </ul>
    </div>

</template>
<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm"

    export default {
        name: "BookList",
        data: function() {
            return {
                title: "All Books",
                books: [
                    {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
                    {title: 'American Gods', author: 'Neil Gaiman'},
                    {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
                ]
            }
        },
        methods: {
            appendBook: function(bookTitle, bookAuthor){
                this.books.push({ title: bookTitle, author: bookAuthor });
            }
        },
        components: {
            BookItem,
            BookForm,
        }
    }
</script>
<style>
h1, h2 {
   font-weight: normal; 
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: block;
    margin: 0 10px;
}
</style>