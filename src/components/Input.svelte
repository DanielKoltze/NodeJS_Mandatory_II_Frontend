<script>
    export let type = "text"
    export let labelText = ""
    export let value = ""

    function handleInput(event){
        value = event.target.value
    }
    
</script>

    <input id="input" type={type} placeholder={labelText} value={value} on:input={handleInput}/>



<style>

input{
    font-size: 16px;
    display: block;
    font-family: 'Rubik', sans-serif;
    width: 100%;
    padding: 10px 1px;
    border: 0;
    border-bottom: 1px solid #747474;
    outline: none;
    transition: all .2s;
    margin: 6px 0px;
}

input:focus{
    border-bottom: 2px solid #000000;
}
</style>