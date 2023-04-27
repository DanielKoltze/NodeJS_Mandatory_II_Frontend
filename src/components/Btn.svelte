<script>
    export let value = ""
    export let onclick = null
    export let type = "submit"
</script>



<input on:click={onclick} type={type} value="{value}">

<style>
    input{
    display: inline-block;
    padding: 10px 20px;
    font-size: 20px;
    font-weight: bold;
    text-transform: uppercase;
    color: #fff;
    background-color: rgb(57, 165, 57);
    border: none;
    border-radius: 5px;
    cursor: pointer;
    margin: 0;
}
input:hover {
  background-color: rgb(34, 123, 34);
}
    
</style>