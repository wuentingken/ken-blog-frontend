<template>
  <Layout>
      <h1>{{post.title}}</h1>
      <div>{{post.content}}</div>
  </Layout>
</template>

<page-query>
    query($id: ID!) {
        post (id: $id) {
            id
            title
            content
        }
    }
</page-query>

<script>
export default {
    name: 'postpage',
    metaInfo () {
        return {
            title: this.$page.post.title
        }
    },
    mounted() {
        console.log(this.$page.post)
    },
    computed : {
        post: function() {
            return this.$page.post
        }
    }
}
</script>

<style>

</style>