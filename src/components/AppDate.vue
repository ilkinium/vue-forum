<template>
  <span :title="timestamp | humanFriendlyDate">
    {{timestamp | diffForHumans}}
  </span>
</template>

<script>
  import moment from 'moment'
  export default {
    name: 'AppDate',
    props: {
      timestamp: {
        required: true,
        type: Number
      }
    },
    filters: {
      humanFriendlyDate (date) {
        return moment.unix(date).locale('az').format('MMMM Do YYYY, HH:mm:ss')
      },
      diffForHumans (date) {
        return moment.unix(date).fromNow()
      }
    }
  }
</script>

<style scoped>

</style>
