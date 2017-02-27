<template>
    <div>
        <ul class="uk-list uk-list-divider">
            <li v-bind:class="{ 'completed': todo.completed }" v-for="(todo, index) in todos">
                <!-- Notice: v-bind:class 表示的是绑定该元素的某一 property - 这里用到了三元运算符，即当 todo.completed 为 true 时，class="completed" -->
                {{ todo.title }}
                <div class="uk-align-right">
                    <button v-on:click="completeTodo( todo )" class="uk-button uk-button-small" v-bind:class="[ todo.completed ? 'uk-button-secondary' : 'uk-button-primary']">
                        {{ todo.completed ? '取消' : '完成' }}
                    </button>
                    <!-- Notice: { ? : } 的用法：当 todo.completed == true 时，执行（输出） ? 后的内容，否则执行（输出） : 后的内容。 -->
                    <button v-on:click="todos.splice(index, 1)" class="uk-button uk-button-danger uk-button-small">删除</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script type="text/javascript">
export default {
    name: 'todos',
    props: ['todos'],
    methods: {
        completeTodo(todo) {
            todo.completed = !todo.completed; // Toggle boolean
        }
    }
}
</script>
