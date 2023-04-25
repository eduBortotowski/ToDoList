<template>
    <div class="container">
        <HeaderContent></HeaderContent>
        <BodyContent></BodyContent>
    </div>
</template>
<script>
    import HeaderContent from './header.vue'
    import BodyContent from './bodyContent.vue'

    export default {
        name: 'ToDoApp',
        components: {
            HeaderContent,
            BodyContent,
        }
    }
</script>
<style>
    * {padding:0; margin:0; box-sizing:border-box;}
    body {background-color:#f9efef;}
    .container {width:93%; height:auto; padding:2%; padding-top:4%; margin:0 auto; text-align:center;}
</style>