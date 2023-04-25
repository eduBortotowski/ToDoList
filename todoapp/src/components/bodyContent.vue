<template>
    <div>
        <div class="bodyContent">
            <form @submit.prevent="submitTask">
                <input type="date" id='dataTarefa' v-model="dataTask">
                <input type="text" id="textTarefa" placeholder="Tarefa..." v-model="contentTask">
                <input type="submit" value="salvar">
            </form>
        </div>
        <div v-for="(tarefa, index) in tasks" :key="index">
            <div v-if="tarefa.status == 0" class="bodyTask Pendding" @click="changeStatus(tarefa, index)">
                <div class="bodyTaskLeft">
                    <span style="color:#f05353;">{{ tarefa.data }}</span>
                </div>
                <div class="bodyTaskCenter">
                    <p>{{ tarefa.conteudo }}</p>
                </div>
                <div class="bodyTaskRight">
                    <a href="" @click.prevent="deleteTask(index)">&#10006;</a>
                </div>
            </div>
            <div v-else-if="tarefa.status == 1" class="bodyTask Executting" @click="changeStatus(tarefa, index)">
                <div class="bodyTaskLeft">
                    <span style="color:#f0b253;">{{ tarefa.data }}</span>
                </div>
                <div class="bodyTaskCenter">
                    <p>{{ tarefa.conteudo }}</p>
                </div>
                <div class="bodyTaskRight">
                    <a href="" @click.prevent="deleteTask(index)">&#10006;</a>
                </div>
            </div>
            <div v-else-if="tarefa.status == 2" class="bodyTask Finished" @click="changeStatus(tarefa, index)">
                <div class="bodyTaskLeft" style="border-right:1px solid #121212;">
                    <span style="color:#9d9c99;">{{ tarefa.data }}</span>
                </div>
                <div class="bodyTaskCenter" style="border-right:1px solid #121212;">
                    <p>{{ tarefa.conteudo }}</p>
                </div>
                <div class="bodyTaskRight">
                    <a href="" @click.prevent="deleteTask(index)">&#10006;</a>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'BodyContent',
        data() {
            return {
                tasks: [],
                dataTask: "",
                contentTask: ""
            }
        },
        methods: {
            formatDate(date){
                let newDate = date.split("-")
                let dateFormated = newDate[2] + "/" + newDate[1] + "/" + newDate[0]
                return dateFormated
            },
            changeStatus(task, index){
                let newIndex = task.status + 1
                if(task.status === 2)  {
                    return task.status = 0
                }
                task.status = newIndex
                console.log(task.status, index)
            },
            deleteTask(index){
                this.tasks.splice(this.tasks.indexOf(index, 1));
            },
            submitTask(){
                if(this.dataTask.length === 0 || this.contentTask.length === 0){
                    return;
                }else {
                    this.tasks.push({
                        data: this.formatDate(this.dataTask),
                        conteudo: this.contentTask,
                        status: 0
                    });
                }
            }
        }
    }
</script>
<style>
    .bodyContent {
        width:100%;
        height:auto;
        padding:1%;
        background-color:white;
        border:1px solid #f2f2f2;
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
        background:none;
        color:#333;
        border:1px solid #efefef;
    }
    .bodyContent form input[type=text] {
        width:40%;
        height:35px;
        padding:1%;
        border:1px solid #efefef;
        margin:1%;
        background:white;
        color:#333;
    }
    .bodyContent form input[type=submit] {
        width:25%;
        height:35px;
        padding:1%;
        border:1px solid #efefef;
        background: rgb(34,195,193);
        font-size:'Open Sans', sans-serif;
        font-size:12pt;
        color:white;
        border-radius:2px;
        font-weight:bold;
    }
    .bodyContent form input[type=submit]:hover {
        cursor:pointer;
    }
    .bodyTask {
        width:98%;
        height:auto;
        margin: 0 auto;
        padding:1%;
        margin:1%;
        background-color:rgb(31, 27, 36);
        border-radius:2px;
        display:table;
    }
    .bodyTask:hover {
        cursor:pointer;
    }
    .Pendding {
        background:white;
        border-left:8px solid #f05353;
        background: rgba(247,71,71,0.1);
        
    }
    .Executting {
        background:white;
        border-left:8px solid #f0b253;
        background: rgba(242,178,110,0.1);
    }
    .Finished {
        background:white;
        background:rgba(40,39,39,0.1);
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
        font-size:auto;
        color:#22c3c1;
        text-align:center;
        vertical-align:middle;
        font-weight:bold;
        letter-spacing:0.05rem;
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
        color:#555555;
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
        border-radius:5px;
        margin:2%;
        text-decoration:none;
    }
    .bodyTaskRight a:hover {
        color:white;
        background:#f05353;
        border:1px solid #f05353;
    }
</style>