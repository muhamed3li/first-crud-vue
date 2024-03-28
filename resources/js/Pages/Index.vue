<template>
  <div class="container mx-auto pt-5">
    <Link :href="`/post/create`">Create Post</Link>

    <div class="post_block" v-for="post in posts" :key="post.id">
      <h2>{{ post.title }}</h2>
      <p>
        <strong>Author: </strong> {{ post.author }} |
        <strong>Published at: </strong> {{ post.created_at }}
        <br />
        <Link :href="`/post/${post.id}`">Read More</Link>
        <br>
        <Link :href="`/post/${post.id}/edit`">Edit Post</Link>
        <br>
        <Link :href="`/post/${post.id}/delete`" method="delete">Delete Post</Link>

      </p>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
import { Link } from "@inertiajs/vue3";
defineProps({
  posts: Object,
});
</script>  
 