<template>
  <div class="hello">
    <p>{{ name }}</p>
    <p>数量：{{ count > 30000 ? "nb666" : "lj777" }}</p>
    姓名：<input type="text" :value="name" />
    <input type="button" value="保存" @click="save" />
  </div>
</template>

<script>
/**
 * HelloWorld组件 - 演示Vue基础组件功能
 * @description 包含基本的数据绑定、条件渲染和事件处理
 */
export default {
  name: "HelloWorld",
  /**
   * 组件接收的属性
   */
  props: {
    msg: String,
  },
  /**
   * 组件数据
   */
  data() {
    return {
      name: "郝思远", // 用户名称
      count: 3025666, // 演示用数量值，用于条件渲染
    };
  },
  /**
   * 组件方法
   */
  methods: {
    /**
     * 保存按钮点击事件处理
     */
    save() {
      alert("保存成功");
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