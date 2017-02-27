<!-- 
  Todos 应用思路：
    
-->
<style type="less">
    .completed { text-decoration: line-through; }
</style>
<template>
    <div class="hello">
        <div class="uk-container-small uk-container uk-margin-large-top">
            <div class="uk-card uk-card-default uk-card-body">
                <h3 class="uk-card-title">待办事项<span class="uk-badge uk-margin-small-left">{{ todoCount }}</span></h3>
                <todos :todos="todos">
                </todos>
            </div>
            <div class="uk-card uk-card-primary uk-card-body uk-margin-large-top">
                <h3 class="uk-card-title">添加事项</h3>
                <todo-form :todos="todos"></todo-form>
            </div>
        </div>
    </div>
</template>
<script>
import Todos from '@/components/Todos'
import TodoForm from '@/components/TodoForm'
export default {
    name: 'hello',
    data() {
        return {
            todos: [{
                id: 1,
                title: 'First Commit',
                completed: false
            }]
        }
    },
    components: {
        Todos,TodoForm
    },
    computed: {
        todoCount() {
            return this.todos.length;
        }
    }
    // data 应为一个函数而非对象
}
</script>
