<script>
import Navbar from "$lib/components/Navbar.svelte";
import axios from 'axios'
let url=" "
let shorturl = "https://trim-url.vercel.app/";
async function sendReq (){
    const response = await axios.post("https://url-shortener-manitej66.azurewebsites.net/api/shorten?code=USDsXCIeE0UKKJTi9pMWHTyQOFWIu2zAOmWmzcAW7PorrkqDeOcnHQ==",{"url":url});
    shorturl =shorturl + response.data.shortUrl;
}
</script>
<Navbar/>
<div class="main">
    <input bind:value={url} type="text" placeholder="enter long url" alt=" ">
    <button on:click={sendReq}>SHORTEN &#9989;</button>
    <h4>CLICK HERE &#10164;</h4>
    <a href = "{url}">{shorturl}</a>
</div>
<style>
    .main{
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 5px;
        flex-direction: column;
    }
    input{
        padding: 20px;
        width: 40%;
        border-radius: 15px;
        font-size: 15px;
        background-color: rgb(234, 255, 149);
        border: none;
        outline: none;
    }
    button{
        padding: 15px;
        margin-top: 20px;
        background-color: black;
        color: burlywood;
        border-radius:10px;
        border: none;
    }
</style>