<template>
    <div class="bckHeader">
        <h1>Lista de tarefas</h1>
        <span>{{ currentDate() }}</span>
    </div>
</template>
<script>
    export default {
        name: 'HeaderContent',
        methods: {
            currentDate() {
                const current = new Date();
                var mes = current.getMonth() + 1
                if(mes == 1){
                    mes = 'Janeiro'
                } else if(mes == 2) {
                    mes = 'Fevereiro'
                } else if(mes == 3) {
                    mes = 'Março'
                } else if(mes == 4) {
                    mes = 'Abril'
                } else if(mes == 5) {
                    mes = 'Maio'
                } else if(mes == 6) {
                    mes = 'Junho'
                } else if(mes == 7) {
                    mes = 'Julho'
                } else if(mes == 8) {
                    mes = 'Agosto'
                } else if(mes == 9) {
                    mes = 'Setembro'
                } else if(mes == 10) {
                    mes = 'Outubro'
                } else if(mes == 11) {
                    mes = 'Novembro'
                } else if(mes == 12) {
                    mes = 'Dezembro'
                }
                const date = `${current.getDate()}, ${mes} de ${current.getFullYear()}`;
                return date;
            }
        }
    }
</script>
<style>
    .bckHeader {
        width:100%;
        height:auto;
        padding:2%;
        border-top-left-radius:7px;
        border-top-right-radius:7px;
        text-align:center;
        background: rgb(34,195,193);
        background: linear-gradient(to left, rgba(34,195,193,1) 0%, rgba(45,253,237,1) 100%);
    }
    .bckHeader h1 {
        font-family:'Open Sans', sans-serif; font-size:22pt; color:white; font-weight:bold;
    }
    .bckHeader span {
        font-family:'Open Sans', sans-serif; font-size:11pt; color:white; font-weight:bold;
    }
</style>