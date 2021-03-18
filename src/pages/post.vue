<template>
  <Layout>
      <h1>文章列表</h1>
      <ul>
            <li v-for="item in $page.posts.edges" :key="item.node.id">
                <g-link :to="item.node.path">{{item.node.title}}</g-link>
            </li>
      </ul>
  </Layout>
</template>

<page-query>
    query {
        posts: allPost {
            edges {
                node {
                    id
                    title
                    path
                }
                }
            }
        }
</page-query>

<script>
import axios from 'axios'

export default {
    name: 'post',
}
</script>

<style>

</style>