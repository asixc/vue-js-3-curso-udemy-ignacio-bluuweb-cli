<template>
    <div>
       <button @click="click" :disabled="desactivar">{{ action }}</button>
    </div>
</template>
<script>
export default {
    props: {
        action: String,
        desactivar: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        click() {
            this.$emit('accion');
        }
    }
}
</script>
<style scoped>
    
</style>