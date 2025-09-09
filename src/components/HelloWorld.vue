<template>
  <!-- 组件根元素，使用hello类名进行样式定义 -->
  <div class="hello">
    <!-- 显示用户姓名信息 -->
    <p>姓名：{{ name }}</p>

    <!-- 使用三元表达式进行条件渲染，根据count值显示不同内容 -->
    <!-- 如果count大于30000则显示"nb666"，否则显示"lj777" -->
    <p>数量：{{ count > 30000 ? "nb666" : "lj777" }}</p>

    <!-- 保存按钮，点击时触发save方法 -->
    <input type="button" value="保存" @click="save" />
    <br />

    <!-- 基础输入框，使用v-model进行双向数据绑定，绑定到name属性 -->
    基础输入框:<input type="text" v-model="name" />
    <br />

    <!-- 性别输入框，使用v-model进行双向数据绑定，绑定到sex属性 -->
    请输入性别（男1女0）:<input type="text" v-model="sex" />
    <br />

    <!-- 单向绑定测试，使用:value指令将name属性值绑定到输入框 -->
    <!-- 注意：此处仅为演示单向绑定，实际使用中输入框内容变化不会影响name值 -->
    双向绑定测试:<input type="text" :value="name" />

    <!-- 条件渲染示例，根据sex属性值显示不同内容 -->
    <div v-if="sex == 1">男</div>
    <!-- 当sex等于1时显示"男" -->
    <div v-else-if="sex == 0">女</div>
    <!-- 当sex等于0时显示"女" -->
    <div v-else>未知</div>
    <!-- 当sex为其他值时显示"未知" -->

    <input type="button" value="发送请求" @click="sendRequest" />
  </div>
</template>

<script>
import axios from "axios";
/**
 * HelloWorld组件
 * @description Vue.js基础演示组件，用于展示数据绑定、条件渲染和事件处理等核心功能
 * @author 系统自动生成
 * @date 2023-11-21
 */
export default {
  /**
   * 组件名称
   * @type {string}
   */
  name: "HelloWorld",

  /**
   * 组件接收的外部属性
   * @property {string} msg - 可选的消息属性，用于从父组件接收数据
   */
  props: {
    msg: String,
  },

  /**
   * 组件内部数据
   * @returns {Object} 包含组件所有响应式数据的对象
   */
  data() {
    return {
      /**
       * 用户名称
       * @type {string}
       * @default "郝思远"
       */
      name: "郝思远",

      /**
       * 演示用数量值，用于条件渲染判断
       * @type {number}
       * @default 3025666
       */
      count: 3025666,

      /**
       * 用户性别标识（1:男, 0:女）
       * @type {number}
       * @default 1
       */
      sex: 1,
    };
  },

  /**
   * 组件方法集合
   */
  methods: {
    /**
     * 保存按钮点击事件处理函数
     * @description 点击保存按钮时弹出提示信息
     * @returns {void}
     */
    save() {
      // 显示保存成功的提示信息
      alert("保存成功");
    },
    /**
     * 发送请求按钮点击事件处理函数
     * @description 点击发送请求按钮时发送POST请求到后端
     * @returns {void}
     */
    sendRequest() {
      axios.post("/api/hello").then((res) => {
        console.log(res.data);
      });
    },
  },

  /**
   * 组件生命周期钩子 - 创建完成
   * @description 组件实例创建完成后调用，此时组件数据已经观测，但尚未挂载DOM
   * @returns {void}
   */
  created() {
    // 组件创建时可以进行初始化操作
    // console.log('组件已创建');
  },

  /**
   * 组件生命周期钩子 - 挂载完成
   * @description 组件挂载到DOM后调用，此时可以访问DOM元素
   * @returns {void}
   */
  mounted() {
    // 组件挂载后可以进行DOM操作
    // console.log('组件已挂载到DOM');
  },
};
</script>

<!-- 添加"scoped"属性使CSS样式仅应用于当前组件 -->
<!-- 这样可以避免样式污染全局或其他组件 -->
<style scoped>
/* 标题样式 */
h3 {
  margin: 40px 0 0;
}

/* 无序列表样式 */
ul {
  list-style-type: none; /* 移除默认列表样式 */
  padding: 0; /* 移除默认内边距 */
}

/* 列表项样式 */
li {
  display: inline-block; /* 水平排列 */
  margin: 0 10px; /* 左右边距 */
}

/* 链接样式 */
a {
  color: #42b983; /* 设置链接颜色 */
}
</style>