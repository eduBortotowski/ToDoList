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
    body {background-color:#121212;}
    .container {width:93%; height:auto; padding:2%; padding-top:4%; margin:0 auto; text-align:center;}
</style>