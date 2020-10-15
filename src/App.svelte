<script context="module">
    import CreateTask from './components/CreateTask.svelte' 
    import Task from './components/Task.svelte'
    import { tasks } from "./store.js";
    import { onDestroy } from "svelte";
</script>
<script>

    // let task = []

    // const unsubscribe = tasks.subscribe(value =>{
    //     task = value
    // })
    // onDestroy(()=>{
    //     unsubscribe()
    // })
    $: console.log($tasks)
    // function addNewTask(e) {
    //     task = [e.detail, ...task]
    // }

</script>
<svelte:head>
    <!-- CSS only -->
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">
    <title>Svelte Learning</title>
</svelte:head>
<div class="container">
    <div class="row">

        <div class="col-md-6 offset-md-3 my-4">
            <h1>Hello LinuxBD</h1>
            <!-- <CreateTask on:taskCreated={addNewTask} /> -->
            <CreateTask />
            <Task taskList = {$tasks} />
        </div>
    </div>

</div>