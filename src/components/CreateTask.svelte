<script>
    import {tasks } from "../store.js";
    // import {createEventDispatcher} from 'svelte'
    import Color from './Color.svelte'

    // const dispatch = createEventDispatcher()
    let title = ''
    let description = ''
    let color = 'orange'

    function submitHandler(e) {
        if (!title) {
            alert("Provide a Title")
            return
        }
        let id = (Math.random() * new Date().getTime()).toString()
        let task = {
            id,
            title,
            description,
            color,
            completed:false,
            editable:false
        }
        // dispatch('taskCreated',task)
        let newTasks = [task, ...$tasks]
        tasks.set(newTasks)

        e.target.reset() 
        //color = ''
    }
</script>

<div class="card, card-body my-4">
    <form on:submit|preventDefault={submitHandler}>
        <div class="form-group">
            <label for="title">Enter a Task Title</label>
            <input type="text" placeholder="Task Title" id="title" class="form-control" bind:value={title}>

        </div>
        <div class="form-group">
            <label for="desc">Enter a Short Description</label>
            <textarea id="desc" class="form-control"  bind:value={description}></textarea>

        </div>
        <Color bind:selectedColor={color}/>
        <input type="submit" class="btn btn-primary my-4" value="Create Task">
    </form>
</div>