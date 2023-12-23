<template>
    <div>
        <label v-custom-font.lg.red>Subtotal: </label>
        <input type="number" v-model="subtotal" />
        <h3>Total impuestos a pagar: {{ totalVat }} ({{ vat }}%)</h3>
    </div>
</template>
<script lang="ts" setup>
import { Ref, ref ,computed} from "vue";

/*
CALCULO DE IMPUESTOS
*/
    const vat = 18
    let subtotal:Ref<number> = ref(0)

    const totalVat = computed(()=> vat*subtotal.value/100 )
</script>
<style scoped>
</style>