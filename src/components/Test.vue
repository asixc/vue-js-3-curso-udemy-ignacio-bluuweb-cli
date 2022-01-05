<template>
    <div>
        <h3>Mensaje: {{ msg }}</h3>
    </div>
</template>
<script>
export default {
    name: 'Test',
    props: {
        msg: String
    }
}
</script>
<style scoped>
    
</style>