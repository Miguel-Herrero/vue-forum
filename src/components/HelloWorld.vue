<template>
  <div class="col-full">
    <h1>Welcome to the Forum</h1>
    <ThreadList :threads="threads" />
  </div>
</template>

<script>
import sourceData from '@/data'
import ThreadList from '@/components/ThreadList'

export default {
  name: 'HelloWorld',

  data () {
    return {
      threads: Object.values(sourceData.threads),
      posts: sourceData.posts,
      users: sourceData.users
    }
  },

  components: {
    ThreadList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
