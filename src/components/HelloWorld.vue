<template>
  <div class="hello">{{ name }}</div>

  <table>
    <tr>
      <td>Title</td>
      <td>Completed ?</td>
    </tr>
    <tr v-for="item in data" :key="item.id">
      <td>{{ item.title }}</td>
      <td>{{ item.completed }}</td>
    </tr>
  </table>
</template>

<script>
import axios from "axios";
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "Sagar",
      data: {},
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    getData: function () {
      this.name = "Munot";
      axios.get("https://jsonplaceholder.typicode.com/todos").then((res) => {
        this.data = res.data;
        console.log(this.data);
      });
    },
  },
};
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
