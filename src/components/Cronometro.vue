<template>
    <section>
        <strong>{{ tempoDecorrido }}</strong>
    </section>
</template>


<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'CronoMetro',
    props: {
        tempoEmSegundos: {
            type: Number,
            default: 0
        }
    },
    computed: {
        tempoDecorrido(): string {
            return new Date(this.tempoEmSegundos * 1000).toISOString().substring(11, 19)
            // new Date().toLocaleTimeString() // já retorna o horário, localizado de acordo com o idioma do navegador e não precisa do substring
        }
    },
})

</script>