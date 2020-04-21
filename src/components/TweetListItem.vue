<template lang="html">
  <ul class="tweet-card">
    <li id="person-card">{{tweetComponentRef.name}}
      <img v-bind:src="tweetComponentRef.img" alt="Profile Picture">
      <br> {{tweetComponentRef.handle}}</li>
    <br>
    <li>"{{tweetComponentRef.tweet}}"</li>
    <li v-bind:class="tweetHighlightLike">{{tweetComponentRef.likes}} likes</li>

  </ul>
</template>


<script>

export default {
  name: "tweet-list-item",
  props: ['tweetComponentRef'],
  computed: {
    tweetHighlightLike: function () {
      return (this.tweetComponentRef.likes >= 12) ? 'big-licks' : 'small-licks'
    }
  }
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

.big-licks {
  background-color: gold;

}


</style>
