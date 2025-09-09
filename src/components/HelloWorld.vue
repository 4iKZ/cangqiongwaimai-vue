<template>
  <div class="hello">
    <p>{{ name }}</p>
    <p>数量：{{ count }}</p>
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
  // 组件的本地数据
  // data 必须是一个函数，且该函数必须返回一个对象
  // 这样每个组件实例可以维护一份被返回对象的独立的拷贝
  // 如果 data 是一个对象，则所有组件实例将共享同一个对象
  data() {
    return {
      name: "张三",
      count: 0,
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
