<script>
    import { Button, Checkbox } from 'svelte-mui';
    let checked = true;
</script>

<div>
    This is a login page
    <input type="text"/>
    <input type="password"/>
    <button>Submit</button>
</div>

<Checkbox bind:checked>Checkbox</Checkbox>
<Button
outlined
shaped
color="Red"
on:click={() => { checked = !checked }}
>
Inverse
</Button>