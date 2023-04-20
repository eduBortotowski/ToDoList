<template>
    <div v-for="(tarefa, index) in tasks" :key="index">
        <div v-if="tarefa.status == 0" class="bodyTask Pendding">
            <div class="bodyTaskLeft">
                <span style="color:#f05353;">{{ tarefa.data }}</span>
            </div>
            <div class="bodyTaskCenter">
                <p>{{ tarefa.conteudo }}</p>
            </div>
            <div class="bodyTaskRight">
                <a href="">&#9778;</a>
            </div>
        </div>
        <div v-else-if="tarefa.status == 1" class="bodyTask Executting">
            <div class="bodyTaskLeft">
                <span style="color:#f0b253;">{{ tarefa.data }}</span>
            </div>
            <div class="bodyTaskCenter">
                <p>{{ tarefa.conteudo }}</p>
            </div>
            <div class="bodyTaskRight">
                <a href="">&#9778;</a>
            </div>
        </div>
        <div v-else-if="tarefa.status == 2" class="bodyTask Finished">
            <div class="bodyTaskLeft" style="border-right:1px solid #121212;">
                <span style="color:#9d9c99;">{{ tarefa.data }}</span>
            </div>
            <div class="bodyTaskCenter" style="border-right:1px solid #121212;">
                <p>{{ tarefa.conteudo }}</p>
            </div>
            <div class="bodyTaskRight">
                <a href="">&#9778;</a>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'bodyTask',
        data() {
            return {
                statusTask: ['Pendente', 'Em desenvolvimento', 'Concluído'],
                tasks: [
                    {
                        data: '19/04/2023',
                        conteudo: 'Finalizar desenvolvimento do ToDo List',
                        status: 0
                    },
                    {
                        data: '19/04/2023',
                        conteudo: 'Validar informações Slip Gang para o dia 13/04',
                        status: 1
                    },
                    {
                        data: '19/04/2023',
                        conteudo: 'Validar informações Slip Pompeia para o dia 20/04',
                        status: 2
                    }
                ]
            }
        }
    }
</script>
<style>
    .bodyTask {
        width:98%;
        height:auto;
        margin: 0 auto;
        padding:1%;
        margin:1%;
        background-color:#1f1b24;
        border-radius:2px;
        display:table;
    }
    .Pendding {
        border-left:8px solid #f05353;
        
    }
    .Executting {
        border-left:8px solid #f0b253;
    }
    .Finished {
        background:#332940;
        color:white;
        border-left:8px solid #282727;
    }
    .Finished p {
        text-decoration:line-through;
    }
    .bodyTaskLeft {
        width:15%;
        height:auto;
        padding:1%;
        display:table-cell;
        border-right:1px solid #9d9c99;
    }
    .bodyTaskLeft span {
        font-family:'Open Sans', sans-serif;
        font-size:15pt;
        color:#22c3c1;
        text-align:center;
        vertical-align:middle;
    }
    .bodyTaskCenter {
        width:70%;
        height:auto;
        padding:1%;
        border-right:1px solid #9d9c99;
        display:table-cell;
    }
    .bodyTaskCenter p {
        font-family:'Open Sans', sans-serif;
        font-size:12pt;
        color:#9d9c99;
        text-align:center;
        letter-spacing:0.05rem;
        vertical-align:middle;
    }
    .bodyTaskRight {
        width:15%;
        height:auto;
        padding:1%;
        display:table-cell;
    }
    .bodyTaskRight a {
        font-family:'Open Sans', sans-serif;
        font-size:auto;
        background:none;
        border:1px solid #9d9c99;
        color:#9d9c99;
        padding:10px;
        border-radius:2px;
        margin:2%;
        text-decoration:none;
    }
    .bodyTaskRight a:hover {
        color:white;
        background:#22c3c1;
        border:1px solid #22c3c1;
    }
    
</style>