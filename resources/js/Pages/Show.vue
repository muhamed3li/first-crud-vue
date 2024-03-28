<template>
  <div class="show_block">
    <h2>{{ post.title }}</h2>
    <p>{{ post.content }}</p>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
defineProps({
  post: Object,
});
</script>  