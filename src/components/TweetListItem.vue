<template lang="html">
  <ul class="tweet-card">
    <li id="person-card">{{tweetComponentRef.name}} <img v-bind:src="tweetComponentRef.img" alt="Profile Picture"> <br> ({{tweetComponentRef.handle}})</li>
    <br>
    <!-- <li>{{tweetComponentRef.img}}</li> -->
    <li>"{{tweetComponentRef.tweet}}"</li>
    <li>{{tweetComponentRef.likes}} likes</li>

  </ul>
</template>


<script>

export default {
  name: "tweet-list-item",
  props: ['tweetComponentRef']
}

</script>


<style lang="css" scoped>

img {
  width:40px;
  float: left;
  padding: 2px
}

.tweet-card {
  border-style: solid;
  border-width: 4px;
  border-color: DodgerBlue;
  list-style-type: none;
}

#person-card {
  margin:2px
}

</style>
