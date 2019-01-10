<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <book-item v-for="book in books" :key="book.title" :book="book" @deleteBook='spliceBook'></book-item>            
        </ul>
        <book-form @addBook='appendBook'></book-form>
    </div>    
</template>
<script>
import BookItem from './BookItem';
import BookForm from './BookForm';
import { defaultCoreCipherList } from 'constants';

export default {
    name: 'BookList',
    components: {
        BookItem,
        BookForm,
    },
    data() {
        return {
            title: 'All Books',
            books: [
                {
                    title: 'Self-Reliance',
                    author: 'Ralph Waldo Emerson'
                },
                {
                    title: 'American Gods',
                    author: 'Neil Gaiman'
                },
                {
                    title: 'Amusing Ourselves to Death',
                    author: 'Neil Postman'
                }
            ]
        }
    },
    methods: {
        appendBook(bookTitle, bookAuthor) {
            this.books.push({title: bookTitle, author: bookAuthor})
        },
        spliceBook(bookTitle){            
            const foundItens = this.books.filter(a => a.title == bookTitle);
                                    
            for(var i = 0; i < foundItens.length; i++){                
                const index = this.books.indexOf(foundItens[i])
                this.books.splice(index, 1);
            }            
        }
    }
}
</script>
<style>
h1, h2 {
    font-weight: normal;
}

ul {
    list-style-type: none;
    padding: 0
}
</style>