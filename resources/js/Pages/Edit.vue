<template>
  <div class="post_edit">
    <h2>Edit Post</h2>
    <form @submit.prevent="form.put(`/post/${post.id}`)">
      <div>
        <label for="title">Title</label><br />
        <input type="text" v-model="form.title" id="title" /><br />
      </div>
      <div>
        <label for="author">Author</label><br />
        <input type="text" v-model="form.author" id="author" /><br />
      </div>
      <div>
        <label for="content">Content</label><br />
        <textarea v-model="form.content" id="content"></textarea><br />
      </div>
      <button type="submit">Update</button>
    </form>
  </div>
</template>

<script setup>
import { useForm } from "@inertiajs/vue3";
import { defineProps } from "vue";

let props = defineProps({
  post: Object,
});
const form = useForm({
  title: props.post.title,
  author: props.post.author,
  content: props.post.content,
});
</script>