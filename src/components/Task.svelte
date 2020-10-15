<script>
import { tasks } from "../store.js";
import Color from './Color.svelte'


    export let taskList = []
    let label = 'ALL'
</script>
<!-- <div>
    <ul class="list-group">
        {#each task as item}
            <li class="list-group-item">
                {item.title}
            </li>
        {/each}
    </ul>
</div> -->
<style>
    .complete{
        text-decoration: line-through;
    }
    .color{
        height: 10px;
    }
</style>

<div class="my-3">
    <h4>{label} Tasks</h4>
    {#if taskList.length==0}
        <p>There is no Task</p>
    {:else}
        <ul class="list-group">
            {#each taskList as task}
                <li class="list-group-item">
                    <input type="checkbox" class="form-check-input" checked={task.completed}>
                        <label for="">
                            {task.completed?'Done !!!':'Not yet Done'}
                        </label>
                        <input type="text"
                            bind:value={task.title}
                            disabled={!task.editable}
                            class="{task.completed?'form-control complete':'form-control'}"
                        >
                        <div class="color mx-3" title={task.description} style="backgraound:{task.color}">

                        </div>
                </li>
            {/each}
        </ul>
    {/if}
</div>