<template>
    <form class="" action="#" method="post" v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)">
        <input type="text" name="title" value="" placeholder="Book title" v-model="bookTitle">
        <input type="text" name="author" value="" placeholder="Book Auhtor" v-model="bookAuthor">
        <button type="submit" name="button">Add book</button>
    </form>
</template>
<script>
export default {
    name: 'BookForm',
    props: ['books'],
    data() {
        return {
            bookTitle: '',
            bookAuthor: ''
        }
    },
    methods: {
        bookSubmit(bookTitle, bookAuthor) {
            this.$emit('addBook', bookTitle, bookAuthor);
        }
    }
}
</script>
<style>
</style>
