<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-list dense>
        <v-list-item @click="entrar">
          <v-list-item-action>
            <v-icon>mdi-format-list-bulleted</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Lista de Inscritos</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item @click="entra2">
          <v-list-item-action>
            <v-icon>mdi-playlist-edit</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Editar Lista</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Administração</v-toolbar-title>
    </v-app-bar>

  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
    methods:{
      entrar(){
        this.$router.push('usuarios')
      },
      entra2(){
        this.$router.push('usuarios/_id')
      }
    }
    
  }
</script>