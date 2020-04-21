<template lang="html">

  <form v-on:submit.prevent="addNewTodo">
      <label for="add-tweet">New Tweet:</label>
        <input id= "add-todo" type="text" v-model="newTodo"/>
        <label for="priority">High</label>
        <input id= "priority" type="radio" v-model="todoPriority" value="High"/>
        <label for="priority">Low</label>

        <input id= "priority" type="radio" v-model="todoPriority" value="Low"/>
        <button type="submit" name="button">save</button>
    </form>

</template>

<script>
export default {
  name: 'add-tweet'
}
</script>

<style lang="css" scoped>
</style>
