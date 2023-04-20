<template>
    <div class="bodyContent">
        <form action="">
            <input type="date" id='dataTarefa'>
            <input type="text" id="textTarefa" placeholder="Tarefa...">
            <input type="submit" value="salvar">
        </form>
    </div>
</template>
<script>
    export default {
        name: 'BodyContent'
    }
</script>
<style>
    .bodyContent {
        width:100%;
        height:auto;
        padding:1%;
        background-color:#1f1b24;
        border:1px solid #1f1b24;
    }
    .bodyContent form {
        width:70%;
        height:auto;
        padding:1%;
        margin:0 auto;
    }
    .bodyContent form input[type=date] {
        width:33%;
        height:35px;
        padding:1%;
        background:#121212;
        color:white;
        border:1px solid #1f1b24;
    }
    .bodyContent form input[type=text] {
        width:40%;
        height:35px;
        padding:1%;
        border:1px solid #1f1b24;
        margin:1%;
        background:#121212;
        color:white;
    }
    .bodyContent form input[type=submit] {
        width:25%;
        height:35px;
        padding:1%;
        border:1px solid #1f1b24;
        background: rgb(34,195,193);
        font-size:'Open Sans', sans-serif;
        font-size:12pt;
        color:#332940;
        border-radius:2px;
        font-weight:bold;
    }
</style>