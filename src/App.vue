<template>
  <div id="app">
    <!--e-input :valorDeEntrada="numeroDos" @estoyActualizandoAlpadre="actualizarValorEnApp"-->
    <!--e-input
      v-model="numeroDos"
      @estoyActualizandoAlpadre="actualizarValorEnApp"
    /-->
    <e-input v-model="numeroDos" />
  </div>
</template>

<script>
import EInput from "./components/EInput.vue";

export default {
  name: "App",
  components: {
    EInput,
  },
  data() {
    return {
      numeroDos: "2",
    };
  },
  methods: {
    actualizarValorEnApp(valorentrada) {
      console.log("actualizarValorEnApp", valorentrada);
    },
  },
};
</script>
