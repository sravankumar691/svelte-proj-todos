<script lang="ts">
  import { each, prevent_default } from "svelte/internal";
  import TodoItem from "./TodoItem.svelte";
  export let todos:todoType[];
  let value:string='';
  const handleChange=(e)=>{
    value=e.target.value
  }
  const submitForm=()=>{
    todos=[...todos,{
        isCompleted:false,
        uid:Date.now().toString(),
        text:value
    }]
    value=''
  }
</script>

<style>

.card{
    max-width: 42rem;
    text-align: center;
    margin: 0 auto;
    padding: 2em;
}
.card input{
    width: 90%;
    outline: none;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    height: 2.5rem;
    border-radius: 25px;
    font-size: large;
    padding: 0 0.5rem;
    border: none;
    background-color: bisque;
}
.card ul{
    padding: 1em;
    list-style: none;
    text-align: left;
}
.card ul li{
    margin: 1em 0;
}
</style>
<section class="card">
<form on:submit|preventDefault={submitForm}>
    <input bind:value={value} on:change={handleChange} />
</form>
<ul>
   {#each todos as todo }
    <li>
        <TodoItem todo={todo}/>
    </li>
   {/each}
</ul>
</section>