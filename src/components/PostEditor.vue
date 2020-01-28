<template>
  <form @submit.prevent="save">
    <div class="form-group">
      <textarea name="" id="" cols="30" rows="10" class="form-input" v-model="newPostText"></textarea>
    </div>
    <div class="form-actions">
      <button class="btn-blue">submit</button>
    </div>
  </form>
</template>

<script>
  export default {
    name: 'PostEditor',
    props: {
      threadId: {
        required: true
      }
    },
    data () {
      return {
        newPostText: ''
      }
    },
    methods: {
      save () {
        const postId = 'postID-' + Math.random()
        const post = {
          text: this.newPostText,
          publishedAt: Math.floor(Date.now() / 1000),
          threadId: this.threadId,
          userId: 'L664y3qZSubDbT1R6npC0EEybJ73',
          '.key': postId
        }
        this.newPostText = ''

        this.$emit('save-post', {post})
      }
    }
  }
</script>

<style scoped>

</style>
