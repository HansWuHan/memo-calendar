<template>
  <div class="hello">
    <Calendar :events="events"></Calendar>
  </div>
</template>

<script>
import Calendar from './Calendar/Calendar'
export default {
  name: 'HelloWorld',
  components: { Calendar },
  props: {
    msg: String
  },
  data: function () {
    return {
      events: [
        {
          id: "e4",
          startDate: new Date(),
          title: "My Birthday!",
          classes: "birthday",
          url: "https://en.wikipedia.org/wiki/Birthday",
        },
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
