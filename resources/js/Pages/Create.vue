<template>
  <div class="post_create">
    <h1>Create a new post</h1>  
    <form @submit.prevent="form.post('/post')">
        <div>
            <label for="title">Title: </label>  
            <input type="text" id="title" v-model="form.title"/><br/>
        </div>
        <div>
            <label for="author">Author: </label>  
            <input type="text" id="author" v-model="form.author"/><br/>
        </div>
        <div>
            <label for="content">Content: </label>    
            <textarea id="content" v-model="form.content"></textarea><br/>
        </div>
        <button type="submit">Create</button>
    </form>
  </div>
</template>

<script setup>
import { useForm } from "@inertiajs/vue3";
const form = useForm({
  title: "",
  author: "",
  content: "",
});
</script>