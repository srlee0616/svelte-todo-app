<script>
    import { todos }  from '~/store'
    import CreatTodo  from '~/components/CreatTodo'
    import Todo  from '~/components/Todo'

    const storageTodos = localStorage.getItem('todos')
    if (storageTodos) {
        $todos = JSON.parse(storageTodos)
    }
</script>

<div class="container">
    <CreatTodo />
    <div class="todos">
        {#each $todos as todo (todo.id)}
            <!-- <div>{todo.title}</div> -->
            <Todo {todo} />
        {/each}
    </div>
</div>

<style lang="scss">
    .todos {
        padding: 20px 0;
    }
</style>
