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
        { name: "twitter:site", content: "@random" },
        { name: "twitter:card", content: "summary_large_image" },
        {
          hid: "twitter:url",
          name: "twitter:url",
          content: "https://nuxt-sample-app.netlify.app",
        },
        {
          hid: "twitter:title",
          name: "twitter:title",
          content: this.postData.title,
        },
        {
          hid: "twitter:description",
          name: "twitter:description",
          content:
            "Articles focused on the beautiful art of landscape painting.",
        },
        {
          hid: "twitter:image",
          name: "twitter:image",
          content: this.postData.thumbnailUrl,
        },
        { property: "og:site_name", content: "I Love Painting" },
        { hid: "og:type", property: "og:type", content: "website" },
        {
          hid: "og:url",
          property: "og:url",
          content: "https://nuxt-sample-app.netlify.app",
        },
        {
          hid: "og:title",
          property: "og:title",
          content: this.postData.title,
        },
        {
          hid: "og:description",
          property: "og:description",
          content:
            "Articles focused on the beautiful art of landscape painting.",
        },
        {
          hid: "og:image",
          property: "og:image",
          content: this.postData.thumbnailUrl,
        },
        { property: "og:image:width", content: "740" },
        { property: "og:image:height", content: "300" },
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