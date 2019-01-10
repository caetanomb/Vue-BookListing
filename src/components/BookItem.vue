<template>
    <div>
        <li>
            {{ book.title}}:{{book.author}}
            <button type="button" name="deleteButton" v-on:click="deleteBook()">Delete Book</button>
        </li>        
    </div>    
</template>
<script>
    export default {
        name: "BookItem",
        props: ['book'],
        methods: {
            deleteBook() {
                this.$emit('deleteBook', this.book.title);                
            }
        }
    }
</script>
<style>
li {
    display: block;
    margin: 0 10px;
}
</style>