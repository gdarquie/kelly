<script>
    import { Textfield, Button } from 'svelte-mui';
    let login='';
    let password='';
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
        <Button class="submit" outlined color='#db5462'>Submit</Button>
    </div>

    <div>
        {login}{password}
    </div>

</div>