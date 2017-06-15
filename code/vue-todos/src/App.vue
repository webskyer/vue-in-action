<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <ul class="todos">
      <li v-for="(todo,index) in todos" v-bind:class="{'checked': todo.done}">
        <label>{{ index+1 }}.{{ todo.value}}</label>
        <time>{{ todo.created | date }}</time>
      </li>
    </ul>
    </ul>
  </div>
</template>

<script>
import './assets/site.less'
import './assets/todos.less'
import moment from 'moment'
import 'moment/locale/zh-cn'
moment.locale('zh-cn')

export default {
  data() {
    return {
      title: 'vue-todos',
      todos: [
        {
          value: "阅读一本关于前端开发的书",
          done: false,
          created: Date.now()
        },
        {
          value: "补充示例代码",
          done: true,
          created: Date.now()
        },
        {
          value: "写心得",
          done: false,
          created: Date.now()
        }
      ]
    }
  },
  filters: {
    date(val) {
      return moment(val).calendar()
    }
  }
}
</script>

<style>

</style>