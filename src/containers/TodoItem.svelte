<script lang="ts">
    export let todo:todoType
</script>
<style>
    .main{
        display: flex;
        align-items: center;
        justify-content: space-between;
        text-align: left;
        border:1px solid brown;
        border-radius: 25px;
        background-color: blanchedalmond;
    }
    .completed{
        background-color: burlywood;
    }
    .mark{
        border-radius: 25px;
        width: 3rem;
        height: 3rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .mark input[type="checkbox"]{
        width: 60%;
        height: 60%;
        accent-color: burlywood ;
        cursor: pointer;
        background-color: burlywood;
    }
    section p{
        min-width: 40%;
        max-width: 80%;
    }
    .completed p{
        text-decoration: line-through;
    }
    .actions{
        padding: 0 .5em;
        display: flex;
    }
    .actions button{
        background-color: blanchedalmond;
        cursor: pointer;
        border: none;
    }
    .completed .actions button{
        background-color: burlywood;
    }
</style>
<section class={`main ${todo.isCompleted&&'completed'}`} >
    <form class="mark" method="put" action="/todos/update">
        <input type="checkbox" bind:checked={todo.isCompleted}/>
    </form>
    <p>{todo.text}</p>
    <section class="actions">
        <form method="post" action="/todos/save">
            <button type="submit">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="#36454F" class="bi bi-archive" viewBox="0 0 16 16">
                <path d="M0 2a1 1 0 0 1 1-1h14a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1v7.5a2.5 2.5 0 0 1-2.5 2.5h-9A2.5 2.5 0 0 1 1 12.5V5a1 1 0 0 1-1-1V2zm2 3v7.5A1.5 1.5 0 0 0 3.5 14h9a1.5 1.5 0 0 0 1.5-1.5V5H2zm13-3H1v2h14V2zM5 7.5a.5.5 0 0 1 .5-.5h5a.5.5 0 0 1 0 1h-5a.5.5 0 0 1-.5-.5z"/>
            </svg>
        </button>
        </form>
        <form method="delete" action="/todos/del">
            <button>
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="#36454F" class="bi bi-trash" viewBox="0 0 16 16">
                <path d="M5.5 5.5A.5.5 0 0 1 6 6v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5Zm2.5 0a.5.5 0 0 1 .5.5v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5Zm3 .5a.5.5 0 0 0-1 0v6a.5.5 0 0 0 1 0V6Z"/>
                <path d="M14.5 3a1 1 0 0 1-1 1H13v9a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V4h-.5a1 1 0 0 1-1-1V2a1 1 0 0 1 1-1H6a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1h3.5a1 1 0 0 1 1 1v1ZM4.118 4 4 4.059V13a1 1 0 0 0 1 1h6a1 1 0 0 0 1-1V4.059L11.882 4H4.118ZM2.5 3h11V2h-11v1Z"/>
            </svg>
        </button>
        </form>
    </section>
</section>