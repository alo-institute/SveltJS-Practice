<script>
    // import {createEventDispatcher} from 'svelte'
    // const dispatch = createEventDispatcher();

    export let greet = 'Hello';
    export let name = 'Mehejabin Tisha';

    // function nameChangeHandler(e) {
    //     if (e.key == 'Enter') {
    //         dispatch('nameChanged', name);
    //     }
    // }

</script>

<h2><p align="center">{greet}, {name}!</p></h2>
<!-- <input type="text" bind:value={name} on:keypress={nameChangeHandler}> -->
<input type="text" bind:value={name} >