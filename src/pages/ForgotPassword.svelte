<script>
    import Input from "../components/Input.svelte"
    import Btn from "../components/Btn.svelte"

    import toastr from 'toastr'

    let email = ""
    async function postPassword(){
        const setting = {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({
            email
    })}
        const res = await fetch("/api/forgotPassword", setting)
        if(res.status == 404){
            const data = await res.json()
            toastr.error("Mail was not sent")
        }else{
            toastr.success("Mail has been sent")
            
        }
       
    }


</script>
    
    
    <div class="container">
        <div class="border">
            <h1>Forgot password</h1>
            <p class="subheading">Write your email and get a random new password</p>
            <Input labelText="EMAIL" bind:value={email}></Input>
            <p class="forgot"><a href="/login">DO YOU ALREADY KNOW YOUR PASSWORD?</a></p>
            <Btn onclick={postPassword} value="Send email"></Btn>
        </div>
    </div>
    
    
    
    <style>
    
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