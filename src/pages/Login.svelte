<script>
    import Input from "../components/Input.svelte"
    import Btn from "../components/Btn.svelte"
    import toastr from "toastr"

    let email = ''
    let password = ''

    async function login(){
        const setting = {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({
            email,
            password,
    })}
        const res = await fetch("/api/login", setting)
        const message = await res.json()
        if(res.status === 200){
            console.log("redirect")
            window.location.href = "/home"
        }else{
            toastr.error(message.message)
        }
    }

</script>
    
    
    <div class="container">
        <div class="border">
            <h1>Login</h1>
            <p class="subheading">Welcome back! Login with you credentials</p>
            <Input labelText="EMAIL" bind:value={email}></Input>
            <Input labelText="PASSWORD" type="password" bind:value={password}></Input>
            <p class="forgot"><a href="/forgotPassword">FORGOT YOUR PASSWORD?</a></p>
            <div class="btn-container">
               <Btn value="Login" onclick={login}></Btn>
               <a href="/signup" ><Btn value="Sign up"></Btn></a>
            </div>
        </div>
    </div>
    
    
    
    <style>
    
    .btn-container{
        width: 100%;
        display: flex;
        justify-content: space-evenly;
    }
    .subheading{
        color: rgb(88, 86, 86);
        font-size: 14px;
    }
    h1{
        text-align: start;
        margin: 0;
        font-family: 'Rubik', sans-serif;
        font-weight: 400;
    }
    .forgot{
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