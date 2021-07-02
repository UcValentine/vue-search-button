<template>
  <article>
      <img :src="post.img">
    <h3>{{ post.title }}</h3>
    <p>{{post.body}}</p>
  </article>
</template>
<script>
export default {
  props: ["post"]
};
</script>

