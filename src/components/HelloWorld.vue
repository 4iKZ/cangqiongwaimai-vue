<template>
  <div class="hello">
    <p>{{ name }}</p>
    <p>数量：{{ count > 30000 ? "nb666" : "lj777" }}</p>
    姓名：<input type="text" v-bind:value="name" />
  </div>
</template>

<script>
//import { construct } from "core-js/fn/reflect";

export default {
  name: "HelloWorld",
  // 组件接收的 props
  props: {
    msg: String,
  },
  data() {
    return {
      name: "郝思远",
      count: 3025666,
    };
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
