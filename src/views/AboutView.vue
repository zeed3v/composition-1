<template>
  <div class="about">
    <h1
      :style="{'color': color}"
    >Contador: {{contador}}</h1>
    <button @click="aumentar">+</button>
    <button @click="disminuir">-</button>
    <hr>
    <input type="text" v-model="texto">
    <p>{{texto}}</p>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import { computed } from '@vue/runtime-core';
export default {
  setup(){
    const contador = ref(0);
    const texto = ref('')

    const aumentar = () => {
      contador.value ++
    }
    const disminuir = () => {
      contador.value --
    }

    const color = computed(() => {
      if (contador.value < 0){
        return 'red'
      }else{
        return 'blue'
      }
    })

    return {contador, aumentar, disminuir, color, texto}
    
  }
}
</script>

