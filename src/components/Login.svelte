<script>
    import {Textfield, Button} from 'svelte-mui';
    import Indexation from './Indexation.svelte';
    import Import from "./Import.svelte";

    let login = '';
    let password = '';
    let result = null;
    let connected = false;
    let mc3Url = 'http://127.0.0.1:8000/';

    async function postLogin() {
        
        const response = await fetch(mc3Url+'login', {
            method: 'POST',
            headers: {'content-type': 'application/json'},
            body: JSON.stringify({
                "email": login,
                "password": password,
            })
        });

        const json = await response.json()
        result = JSON.stringify(json)
    }

</script>

<style>
    .login-wrapper {
        width: 800px;
        margin: auto;
    }

    p {
        text-align: center;
    }

    .submit-wrapper {
        display: flex;
        justify-content: center;
    }

    .textfields-wrapper {
        margin:auto;
        max-width: 550px;
    }

</style>

<div class="login-wrapper">

    <p>Welcome to the admin page</p>

    <div class="textfields-wrapper">
        <Textfield
            autocomplete="off"
            label="name"
            required
            message="write your login"
            class="login-input login-input-name"
            bind:value={login}
        />

        <Textfield
            autocomplete="off"
            label="password"
            required
            message="write your password"
            class="login-input login-input-password"
            type="password"
            bind:value={password}
        />
    </div>

    <div class="submit-wrapper">
        <Button class="submit" on:click={postLogin} outlined color='#db5462'>Submit</Button>
    </div>

    <Indexation/>
    <Import/>

<!--    <div>-->
<!--        {login}{password}-->
<!--    </div>-->

</div>