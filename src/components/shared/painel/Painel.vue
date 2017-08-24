<template>
    <div class="painel">
        <h2 class="painel-titulo">{{titulo}}</h2>
        <slot class="painel-conteudo"/>
    </div>
</template>

<script>
export default {
    props: ['titulo'],
    
}
</script>

<style lang="scss" scoped>
.painel {
    padding: 0 auto;
    border: solid 1px grey;
    display: inline-block;
    margin: 5px;
    box-shadow: grey 2px 2px 6px;
    width: 200px;
    height: 100%;
    vertical-align: top;
    text-align: center;
}

.painel .painel-titulo {
    text-align: center;
    border-bottom: solid 1px;
    background: lightblue;
    margin: 0 0 15px 0;
    padding: 10px;
    text-transform: uppercase;
    font-weight: normal;
}
</style>
