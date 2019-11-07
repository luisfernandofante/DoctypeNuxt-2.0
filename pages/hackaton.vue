<template>

    <div>
    <app-header />
    <v-parallax
      title="Anúncio do Hackathon"
      dark
      :src="require('assets/planetas-hackathon.jpg')"
      alt="imagem contendo ilustração de planetas e estrelas"
    >
      <h1 class="text-center titulo-parallax">#HACKATHON &lt;!DOCTYPE&gt;</h1>
      <h3 class="text-center sub-parallax">A 12º edição está de outro mundo!</h3>
    </v-parallax>

    <!-- seção que vai o formulário -->
    <section class="contato-section" title="Informação Hackathon">
      <h2 class="section-titulo">{Hackathon}</h2>
      <p class="texto">
        Plunct, Plact, Zum! Não haverá #Hackaton algum... se você não se
        inscrever! Apresse-se e garanta seu passaporte para embarcar na 12º Edição.
        <strong>
          Inscrições válidas até
          <time datetime="”03-12-2019”">03/12</time>
        </strong>.
      </p>
      <img class="patricio" src="../assets/alien.svg" alt="ícone de um alienígena" />
      <!-- aqui vai um formulário -->

  <v-row justify="space-around">
        <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="name"
      :rules="nameRules"
      label="Nome"
      required
    ></v-text-field>

    <v-text-field
      v-model="sobrenome"
      :rules="sobrenomeRules"
      label="Sobre Nome"
      required
    ></v-text-field>

    <v-text-field
      v-model="idade"
      :counter="3"
      :rules="idadeRules"
      label="Idade"
      id="idade"
      required
    ></v-text-field>
    
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>

    <v-select
      v-model="select"
      :items="estado"
      :rules="[v => !!v || 'Estado é Necessário']"
      label="Estado"
      required
    ></v-select>

    
    <v-text-field
      v-model="faculdade"
      :rules="[v => !!v || 'Faculdade é Necessário']"
      label="Faculdade"
      required
    ></v-text-field>

    <v-text-field
      v-model="Curso"
      :rules="[v => !!v || 'Curso é Necessário']"
      label="Curso"
      required
    ></v-text-field>

   

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Enviar
    </v-btn>

    
  </v-form>
  </v-row>
      


    </section>

    <section class="sobre-section" title="Sobre nós">
      <div class="interior-width">
        <div class="sobre-section-linha">
          <div class="sobre-section-coluna">
            <!-- perguntas frequentes-->
            <section class="sobre" title="Perguntas Frequentes">
              <h2 class="section-titulo">f.a.q.</h2>
               
              <ul>
                <li class="servico-desc">
                  <h3 class="servico-titulo">A participação é paga?</h3>Não. A participação do evento é gratuita. No entanto, os custos de
                  viagem, estadia e outros fora do evento são de responsabilidade do
                  participante.
                </li>

                <li class="servico-desc">
                  <h3 class="servico-titulo">O evento é presencial ou online?</h3>O Hackathon é presencial. O nosso Q.G é na Av. Antônio Neudenir Benagna Micali,107 Taquaritinga-SP.
                </li>

                <li class="servico-desc">
                  <h3 class="servico-titulo">Existe um limite de idade para participar?</h3>Sim. Uma vez que a nossa intenção é contratar novos profissionais talentosos, limitamos a participação apenas para pessoas com idade superior a 16 anos.
                </li>

                <li class="servico-desc">
                  <h3 class="servico-titulo">Posso escolher minha equipe?</h3>Não. As equipes serão organizadas no dia na hora do evento. Valorizamos o trabalho em equipe independentemente de quem sejam os envolvidos.
                </li>
                <li class="servico-desc">
                  <h3 class="servico-titulo">As esquipes serão compostas por quantos integrantes?</h3>As equipes terão entre 2 à 5 integrantes no máximo.
                </li>
              </ul>
            </section>
          </div>

          <section class="sobre-section-coluna" title="Datas e horários">
            <div class="conter">
              <div class="content" title="Período de inscrições">
                <p class="servico-titulo-hack">
                  09:00am de
                  <time datetime="”10-11-2019”">10/11</time> à 11:59pm de
                  <time datetime="”03-12-2019”">03/12</time>
                </p>
                <p class="servico-desc">Período de inscrições.</p>
              </div>
              <div class="content" title="Dia do evento">
                <p class="servico-titulo-hack">
                  <time datetime="”10-12-2019”">10/11</time> e
                  <time datetime="”11-12-2019”">03/12</time> das 09:00am às 05:00pm
                </p>
                <p class="servico-desc">12ª edição do #Hackathon 2019</p>
              </div>
              <div class="content" title="Divulgação dos resultados">
                <p class="servico-titulo-hack">
                  A partir da 12:00pm do dia
                  <time datetime="”10-12-2019”">20/12</time>
                </p>
                <p class="servico-desc" >Divulgação dos resultados e equipe vencedora. Não esqueça de verificar seu email!</p>
              </div>
            </div>
          </section>
        </div>
      </div>
    </section>
        <!-- seção que vai o formulário -->
    <section class="contato-section" title="Informação Hackathon">
      <h2 class="section-titulo">{vencedores 2018}</h2>
      <p class="texto">
        Conheça a equipe campeã da 11º edição!
      </p>
      <img class="patricio" src="../assets/alien.svg" alt="ícone de um alienígena" />
      <!-- aqui vai um formulário -->
    </section>

  <app-footer/>
</div>
</template>


<script>
import AppHeader from "../components/AppHeader.vue";
import AppFooter from "../components/AppFooter.vue";

  export default {
    
    components:{
    AppHeader,AppFooter,
  },
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Nome é necessário',
      ],
      sobrenome: '',
      sobrenomeRules: [
        v => !!v || 'Sobre Nome é necessário',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail é necessário',
        v => /.+@.+\..+/.test(v) || 'E-mail não é válido',
      ],
      
      select: null,
      estado: [
        'Acre',
        'Amazonas',
        'São Paulo',
        'Rio de Janeiro',
      ],
      checkbox: false,

      
    }),

    methods: {
      validate () {
        if (this.$refs.form.validate()) {
          this.snackbar = true
        }
      },
    },
//     components: {
//     AppFooter,AppHeader,
//   }
  }
</script>
<style scoped>
p {
  padding-top: 10px;
  /* font-weight: bold; */
}
li {
  list-style: none;
  /* padding-left: 10px; */
}
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