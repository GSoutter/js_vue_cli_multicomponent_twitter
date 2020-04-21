
<template lang="html">
    <div>
      <h1>Tweets</h1>
      <p>Total likes: {{totalLikes}}</p>

      <form v-on:submit.prevent="addTweet">
          <label for="new-todo">New Tweet:</label>

          <label for="user-name">Name</label>
            <input id= "user-name" type="text" v-model="newTweetData.name"/>

          <label for="user-handle">Handle</label>
            <input id= "user-handle" type="text" v-model="newTweetData.handle"/>

          <label for="user-avatar">Avatar</label>
            <select class="" v-model="newTweetData.img">
              <option value="https://semantic-ui.com/images/avatar2/large/molly.png">Molly</option>
              <option value="https://semantic-ui.com/images/avatar2/large/matthew.png">Matthew</option>
              <option value="https://semantic-ui.com/images/avatar2/large/elyse.png">Elyse</option>
            </select>
            <img v-bind:src="newTweetData.img" alt="Profile Picture">
            <br>
          <label for="new-tweet-text">Tweet text</label>
            <input id= "new-tweet-text" type="text" v-model="newTweetData.tweet"/>

          <label for="new-tweet-likes">Likes</label>
            <input id= "new-tweet-likes" type="number" v-model.number="newTweetData.likes"/>

            <button type="submit" name="button">Tweet!</button>
        </form>

        <label for="filter-tweet">filter by likes</label>
          <input id= "filter-tweet" type="text" v-model="filterLikeAmount"/>

      <tweet-list-item v-for="(tweetForLoop, index) in filterTweetLike" :key="index" :tweetComponentRef="tweetForLoop"></tweet-list-item>

    </div>
</template>

<script>

  import TweetListItem from './components/TweetListItem.vue'
  import AddTweet from './components/AddTweet.vue'

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
        ],
        newTweetData: {
          id: "",
          name: '',
          handle: '',
          img: 'https://semantic-ui.com/images/avatar2/large/matthew.png',
          tweet: "",
          likes: 0,
        },
        filterLikeAmount: 0
      }
      },

    components: {
      'tweet-list-item': TweetListItem,
      'add-tweet': AddTweet,
    },

    computed: {
      totalLikes: function () {
        return this.tweetsData.reduce((total, tweet) => total + tweet.likes, 0)
      },
      filterTweetLike: function(){
        return this.tweetsData.filter((tweet) => tweet.likes >= this.filterLikeAmount)

      }

    },
    methods: {
      addTweet: function(){
        this.tweetsData.push(this.newTweetData);
        this.newTweetData = {
          id: "",
          name: '',
          handle: '',
          img: 'https://semantic-ui.com/images/avatar2/large/matthew.png',
          tweet: "",
          likes: 0,
        }
      },

    }



  }
</script>

<style lang="css" scoped>

img {
  width:40px;
  float: left;
  padding: 2px
}

</style>
