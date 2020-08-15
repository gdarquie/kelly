<script>
    import { Button } from 'svelte-mui';
    let result = null
    let mc3Url = 'http://127.0.0.1:8000/';

    async function postImport() {

        const response = await fetch(mc3Url+'api/imports', {
            method: 'POST',
            headers:{'content-type': 'application/json'},
            body: JSON.stringify({})
        });

        const json = await response.json()
        result = JSON.stringify(json)
    }
</script>

<h2>Manage imports</h2>

<div class="indexation-action-wrapper">
    <Button class="submit" on:click={postImport} outlined color='#db5462'>Start Import</Button>
</div>