<template>
    <div id="footer">
        <p>Marcelo de Oliveira Rodrigues. All rights reserved</p>
    </div>
</template>


<script>
export default {
    name:'Footer'
}
</script>

<style scoped>
    *{
        background-color: #1c232d
    }

    #footer{
        height: 5vh;
        min-width: 320px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: hsl(193, 38%, 86%);
    }
</style>