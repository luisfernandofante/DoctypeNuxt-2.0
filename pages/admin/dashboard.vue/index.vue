<template>
  <v-app id="inspire" >
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
    
      <v-list dense >
        <v-list-item @click="entrar">
          <v-list-item-action>
            <v-icon>mdi-format-list-bulleted</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Listagem de usuários</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
      class="grey darken-4"
      justify="space-between"
    >
          <v-app-bar-nav-icon class="white--text" @click.stop="drawer = !drawer" />
          <v-toolbar-title class="white--text">Administração</v-toolbar-title>

          <v-spacer></v-spacer>

          <v-btn  @click="sair">Sair</v-btn>
        
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
      this.$vuetify.theme.dark = false
    },
    methods:{
      entrar(){
        this.$router.push('usuarios')
      },
      sair(){
        this.$router.push('/')
      }
    }
    
  }
</script>
