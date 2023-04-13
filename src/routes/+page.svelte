<script lang="ts">
    import '../globalStyles.css'
    import Card from '../containers/Card.svelte';
    let todos:todoType[]=[{
        isCompleted:false,
        text:"Drink Milk",
        uid:"12132"
    },{
        isCompleted:false,
        text:"Drink Water",
        uid:"121"
    },{
        isCompleted:true,
        text:"Go to Gym",
        uid:"2333"
    }
    ]
</script>
<style>
    h1{
        text-align: center;
    }
</style>
<h1>Svelte Todos</h1>
<Card todos={todos}/>