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
      required: true,
    },
    mask: {
      type: String,
      description: "mascara del string. ej. $",
    },
  },
  methods: {
    onChangeInput(event) {
      let valueToEmit = event.target.value;
      if (this.mask) {
        valueToEmit = valueToEmit.slice(this.mask.length, valueToEmit.legth);
      }
      this.$emit("estoyActualizandoAlpadre", valueToEmit);
    },
  },
  computed: {
    maskValue() {
      return this.mask
        ? `${this.mask}${this.valorDeEntrada}`
        : this.valorDeEntrada;
      /* if (this.mask) {
        return `${this.mask}${this.valorDeEntrada}`;
      } else {
        return this.valorDeEntrada;
      } */
    },
  },
};
</script>
