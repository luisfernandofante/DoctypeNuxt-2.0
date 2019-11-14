<template>
  <div>
    <!-- cabeçalho -->
    <app-header />
    <section class="contato-section" title="Contato">
      <div class="meio-width">
        <h2 class="section-titulo">{Contato}</h2>
        <p>Nosso suporte "Patrício, o Ornitorrinco" adora receber menssagens!</p>
        <img class="etornico" src="../assets/platypus.svg" alt="ícone de um ornitorrinco" />
      </div>

      <v-row justify="space-around">
        <v-form ref="form" v-model="valid" lazy-validation id="formulario">
          <v-text-field v-model="name" :rules="nameRules" label="Nome" required></v-text-field>

          <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>

          <v-text-field v-model="name" :rules="mensagemRules" label="Mensagem" required></v-text-field>

          <button :disabled="!valid" @click="validate" id="button">
            Enviar
          </button>
        </v-form>
      </v-row>
      
    </section>

    <app-footer />
  </div>
</template>

<script>
import AppHeader from "../components/AppHeader";
import AppFooter from "../components/AppFooter";
export default {
  components: {
    AppFooter,
    AppHeader
  },

  data: () => ({
    valid: true,
    name: "",
    nameRules: [v => !!v || "Nome é necessário"],
    mensagem: "",
    mensagemRules: [v => !!v || "Mensagem é necessário"],

    email: "",
    emailRules: [
      v => !!v || "E-mail é necessário",
      v => /.+@.+\..+/.test(v) || "E-mail Não Válido"
    ]
  }),

  
  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.snackbar = true;
      }
    }
  }
};
</script>

<style scoped>
h2::after {
  content: "|";
  opacity: 1;
  display: inline-block;
  animation: pisca 0.7s infinite;
}
@keyframes pisca {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}
</style>