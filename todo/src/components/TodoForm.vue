<template>
    <form v-on:submit.prevent="addTodo( newTodo )" class="uk-form">
        <input class="uk-input uk-margin" v-model="newTodo.title" placeholder="输入内容...">
        <button class="uk-button-primary uk-button uk-margin-top uk-float-right" type="submit">提交内容</button>
    </form>
</template>
<script type="text/javascript">
	export default {
		name: 'todo-form',
	    props: ['todos'],
	    data() {
	        return {
	            newTodo: {
	                id: null,
	                title: '',
	                completed: false
	            }
	        }
	    },
	    methods: {
	        addTodo(newTodo) {
	            this.todos.push(newTodo)
	            this.newTodo = {
	                id: null,
	                title: '',
	                completed: false
	            }
	        }
	    }
	}
</script>
