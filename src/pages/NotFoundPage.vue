<template>
  <div class="col-full" :class="$style['content-centered']">
    <h1 :class="$style['heading-large']">Not Found</h1>
    <p :class="$style['text-large']">
      Oops, page not found!
      <router-link :to="{name: 'Home'}">
        Go To Home Page
      </router-link>
    </p>
  </div>
</template>

<script>
  export default {
    name: 'NotFound'
  }
</script>

<style module>
  .content-centered {
    text-align: center;
    padding: 5em;
  }

  .heading-large {
    font-size: 5em;
  }

  .text-large {
    font-size: 2.5em;
    font-weight: lighter;
  }
</style>
