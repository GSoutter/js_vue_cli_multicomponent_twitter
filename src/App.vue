
<template lang="html">
    <div>
      <h1>Tweets</h1>
      <p>Total likes: {{totalLikes}}</p>
      <tweet-list-item v-for="(tweetForLoop, index) in tweetsData" :key="index" :tweetComponentRef="tweetForLoop"></tweet-list-item>
    </div>
</template>

<script>

  import TweetListItem from './components/TweetListItem.vue'

  export default {
    name: 'app',

    data() {
      return {
        tweetsData:[
          {
            id: 1,
            name: 'James',
            handle: '@jokerjames',
            img: 'https://semantic-ui.com/images/avatar2/large/matthew.png',
            tweet: "If you don't succeed, dust yourself off and try again.",
            likes: 10,
          },
          {
            id: 2,
            name: 'Fatima',
            handle: '@fantasticfatima',
            img: 'https://semantic-ui.com/images/avatar2/large/molly.png',
            tweet: 'Better late than never but never late is better.',
            likes: 12,
          },
          {
            id: 3,
            name: 'Xin',
            handle: '@xeroxin',
            img: 'https://semantic-ui.com/images/avatar2/large/elyse.png',
            tweet: 'Beauty in the struggle, ugliness in the success.',
            likes: 18,
          }
        ]}
      },

    components: {
      'tweet-list-item': TweetListItem
    },

    computed: {
      totalLikes: function () {
        return this.tweetsData.reduce((total, tweet) => total + tweet.likes, 0)
      }
    }

  }
</script>

<style lang="css" scoped>
</style>
