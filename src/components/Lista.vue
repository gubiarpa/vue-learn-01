<template>
    <div>
      <ul class="list-group">
        <li v-for="(fruta, index) in frutasOrdenado" :key="fruta.id" @click="aumentar(index)" class="list-group-item d-flex justify-content-between align-items-center">
          {{ index }} - {{ fruta.nombre }}
          <span class="badge badge-primary badge-pill">{{ fruta.cantidad }}</span>
        </li>
      </ul>
      <button @click="limpiar" class="btn btn-danger btn-block mt-4">Limpiar Lista</button>
    </div>
</template>

<script>
import { mapState, mapMutations } from 'vuex'

export default {
    name: 'Cabecera',
    computed: {
      ...mapState(['frutas']),
      frutasOrdenado(){
        return this.frutas.sort((a, b) => b.cantidad - a.cantidad);
          // esto ordena de mayor a menor
      }
    },
    methods: {
      ...mapMutations(['aumentar', 'limpiar'])
    }
}
</script>