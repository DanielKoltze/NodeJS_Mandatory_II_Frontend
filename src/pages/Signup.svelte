<script>
    import Input from "../components/Input.svelte"
    import Btn from "../components/Btn.svelte"
    import { text } from "svelte/internal"
    import validator from "validator"

    let email = ''
    let password = ''
    let repeatedPassword = ''

    let errorMessage = ""

    async function postSignup(){
        const setting = {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({
            email,
            password,
            repeatedPassword
    })}
        const res = await fetch("/api/signup", setting)
        //fundet på nettet
        if(!validator.isEmail(email)){
            errorMessage = "The given mail is not valid"
        }else if(res.status == 200){
            return window.location.href = "/login"
        }else{
            const data = await res.json()
            errorMessage = data.message
        }
        email = ""
        password = ""
        repeatedPassword = ""
       
        
    }

</script>
    
    
<div class="container">
    <div class="border">
        <h1>Sign up</h1>
        <p class="subheading">Create an accunt it is free</p>
        <Input type="text" labelText="EMAIL" bind:value={email}></Input>
        <Input labelText="PASSWORD" type="password" bind:value={password}></Input>
        <Input labelText="CONFIRM PASSWORD" type="password" bind:value={repeatedPassword}></Input>
        {#if errorMessage}
            <p id="errorMsg">{errorMessage}</p>
        {/if}
        <Btn onclick={postSignup} value="Sign up"></Btn>
        <p class="alreadyAccount">Already have an account? <a href="/login">Login</a></p>
    </div>
</div>
    
    
    
<style>

#errorMsg{
    text-align: start;
    font-size: 10px;
    color: red;
    width: 100%;
}
    
h1{
    text-align: start;
    margin: 0;
    font-family: 'Rubik', sans-serif;
    font-weight: 400;
}
.subheading{
    color: rgb(88, 86, 86);
    font-size: 14px;}
.alreadyAccount{
    cursor: pointer;
}

.border{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 12px;
    background-color: white;
    padding: 50px 70px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    width: 25%;
}
.container{
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: lightgreen;
}



</style>