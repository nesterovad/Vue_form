<template>
    <div id="container">
        <p id="message">Клиент успешно создан!</p>
    </div>
</template>

<script>
export default{
    name: 'Success',
    components: {

    }
}
</script>

<style>
#container{
    width: 50dvw;
    min-width: 200px;
    margin-left: 25dvw;
    margin-top:10px;
    border:1px solid lavender;
    background-color:ghostwhite;
    padding-top: 20px;
}

#message{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color:mediumslateblue;
    font-size: 17px;
    margin-left:20px;
}
</style>