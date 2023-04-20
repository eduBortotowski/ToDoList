<template>
    <div class="container">
        <HeaderContent></HeaderContent>
        <BodyContent></BodyContent>
        <BodyTask></BodyTask>
    </div>
</template>
<script>
    import HeaderContent from './header.vue'
    import BodyContent from './bodyContent.vue'
    import BodyTask from './bodyTask.vue'

    export default {
        name: 'ToDoApp',
        components: {
            HeaderContent,
            BodyContent,
            BodyTask
        }
    }
</script>
<style>
    * {padding:0; margin:0; box-sizing:border-box;}
    body {background-color:#f2f2f2;}
    .container {width:90%; height:auto; padding:1%; margin:0 auto; text-align:center;}
</style>