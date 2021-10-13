<template>
  <div class="post--main">
    <div class="post--image">
      <img class="post--thumbnail" :src="postData.thumbnailUrl" />
    </div>
    <div class="titile">
      <span> Titile : </span> <span> {{ postData.title }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "post",
  head() {
    return {
      title: this.postData.title,
      meta: [
        {
          hid: "twitter:title",
          property: "twitter:title",
          content: this.postData.title,
        },
        {
          hid: "twitter:card",
          property: "twitter:card",
        },
        {
          hid: "twitter:image",
          property: "twitter:image",
          content: this.postData.thumbnailUrl,
        },
      ],
    };
  },
  data() {
    return {
      id: this.$route.params.id,
      posts: this.$store.state.posts,
    };
  },
  computed: {
    postData() {
      return this.posts.find((ele) => {
        return ele.id == this.id;
      });
    },
  },
};
</script>

<style scoped>
.post--main {
  text-align: center;
  margin-top: 10%;
}
</style>