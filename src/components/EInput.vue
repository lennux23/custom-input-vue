<template>
  <input :value="maskValue" @input="onChangeInput" />
</template>

<script>
export default {
  model: {
    prop: "valorDeEntrada",
    event: "estoyActualizandoAlpadre",
  },
  props: {
    valorDeEntrada: {
      type: String,
    },
  },
  methods: {
    onChangeInput(event) {
      this.$emit("estoyActualizandoAlpadre", event.target.value);
    },
  },
  computed: {
    maskValue() {
      return `$ ${this.valorDeEntrada}`;
    },
  },
};
</script>
