<template>
    <div>
        <h1>{{ msg }}</h1>
        <h3>Su saldo es de: {{ saldo }}</h3>
        <h3>Cuenta {{ estado ? 'Activa' : 'Desactivada' }} </h3>
        <div class="lista">
            <p>Servicios contratados:</p>
            <div v-for="(servicio, index) in servicios" :key="index" >
                {{index +1}} - {{ servicio }}
            </div>
        </div>
        <AccionSaldo 
            action="Aumentar saldo" 
            @accion="aumentar"
        />
        <AccionSaldo 
            action="Disminuir saldo"
            @accion="disminuir"
            :desactivar="desactivar"
        />
    </div>
</template>
<script>
import AccionSaldo from './AccionSaldo';

export default {
    name: 'Cuenta',
    props: {
        msg: String
    },
    components: {
        AccionSaldo
    },
    
    data() {
        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: true,
            servicios: ['giro', 'abono', 'transferencia'],
            desactivar: false
        }
    },
    methods: {
        aumentar () {
            this.saldo+= 100;
            this.checkSaldo();
        },
        disminuir() {
            this.saldo-= 100;
            this.checkSaldo();
        },
        checkSaldo(){
            this.desactivar = this.saldo === 0 ? true: false;
        }
    }
}
</script>
<style scoped>
    
</style>