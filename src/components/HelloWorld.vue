<template>
  <div>
    <div class="col-large push-top" v-for="thread in threads" :key="thread['.key']">
      <h1>{{ thread.title }}</h1>
      <div class="post-list">
        <div class="post" v-for="postId in thread.posts" :key="postId">
            <div class="user-info">
                <a href="#" class="user-name">{{ users[posts[postId].userId].name }}</a>

                <a href="#">
                    <img class="avatar-large" :src="users[posts[postId].userId].avatar" alt="">
                </a>

                <p class="desktop-only text-small">107 posts</p>
            </div>

            <div class="post-content">
                <div>
                  <p>{{ posts[postId].text }}</p>
                </div>
            </div>

            <div class="post-date text-faded">
                {{ posts[postId].publishedAt }}
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data'

export default {
  name: 'HelloWorld',
  data () {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
