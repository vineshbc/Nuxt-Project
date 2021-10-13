<template>
  <div>
    <div class="post--title">
      <div v-for="(post, index) in posts" :key="index" class="post--list">
        <NuxtLink :to="{ name: 'post-id', params: {id:post.id} }" class="post--info"
          >{{ post.title }}
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  data() {
    return {
      posts: this.$store.state.posts,
    };
  },
};
</script>

<style scoped>
.post--title {
  margin-top: 5%;
  display: grid;
    grid-template-columns: auto auto auto;
}
.post--info {
  text-decoration: none;
  color: black;
}
.post--list{
  padding: 10px;
    margin: 10px;
    background: coral;
    text-align: center;
}
</style>
