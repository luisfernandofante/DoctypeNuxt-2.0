<template>
  <v-app id="inspire">
    <v-content>
      <v-container
        class="fill-height"
        fluid
      >
        <v-row
          align="center"
          justify="center"
        >
          <v-col
            cols="12"
            sm="8"
            md="4"
          >
            <v-card>
              <v-toolbar
                color="grey darken-4"
                flat
              >
                <v-toolbar-title class="white--text" >Login</v-toolbar-title> 
                <v-spacer></v-spacer>    
              </v-toolbar>

               <v-card-text>
              <v-form>
                <v-text-field v-model="login" label="Usuário" prepend-icon="mdi-face" />
                <v-text-field v-model="password" label="Senha" prepend-icon="mdi-lock" type="password" />
                <v-alert transition="scale-transition" type="error" :value="!!alerta">{{ alerta}}</v-alert>
              </v-form>
            </v-card-text>

           
              <v-card-actions>
                <v-spacer />
                  <v-btn @click="voltar">Voltar</v-btn>
                <v-btn color="primary" @click="acessar">Entrar</v-btn>
              
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    data () {
    return {
      login: '',
      password: '',
      alerta: ''
    }
  },
   methods: {
    acessar () {
      if (this.login === 'Admin' && this.password === '123') {
        this.$ls.set('user', {
          login: this.login,
          nome: 'Admin',
        })
        this.$router.push('/index')
      } else {
        this.alerta = 'Usuário ou senha não correspondentes.'
      }
    },
       voltar(){
      this.$router.push('/')
    }
  },
    props: {
      source: String,
    },

  }
</script>

