<template>
  <div>
    <app-header />
    <v-parallax
      title="Anúncio do Hackathon"
      dark
      :src="require('assets/espaco-hackathon.jpg')"
      alt="imagem contendo ilustração de planetas e estrelas"
    >
      <h1 class="text-center titulo-parallax">#HACKATHON &lt;!DOCTYPE&gt;</h1>
      <h4 class="text-center sub-parallax">A 12º edição está de outro mundo!</h4>
    </v-parallax>



    <section class="sobre-section" title="Hackathon 2019">
      <div class="interior-width">
        <div class="sobre-section-linha">
          <div class="sobre-section-coluna">
        
            <section class="sobre texto" title="Inscrição">
              <h2 class="section-titulo">{Hackathon}</h2>Plunct, Plact, Zum! Não haverá #Hackaton algum... se você não se
              inscrever! Apresse-se e garanta seu passaporte para embarcar na 12º Edição.
              <strong>
                Inscrições válidas até
                <time datetime="”03-12-2019”">03/12</time>
              </strong>.
              <img class="patricio" src="../assets/planet.svg" alt="ícone de planetas" />
            </section>
          </div>

          <section class="sobre-section-coluna" title="Formulário de inscrição">
            <v-row justify="space-around">
              <v-form ref="form" v-model="valid" lazy-validation id="formulario">
                <v-text-field v-model="name" :rules="nameRules" label="Nome" required></v-text-field>

                <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>

                <v-select
                  v-model="select"
                  :items="items"
                  :rules="[v => !!v || 'Estado é Necessário']"
                  label="Estado"
                  required
                ></v-select>

                <v-select
                  v-model="select"
                  :items="items2"
                  :rules="[v => !!v || 'Cidade é Necessário']"
                  label="Cidade"
                  required
                ></v-select>

                <button :disabled="!valid" @click="validate" id="button">Enviar</button>
              </v-form>
            </v-row>
          </section>
        </div>
      </div>
    </section>
    
    <section class="sobre-section">
      <div class="interior-width">
        <div class="sobre-section-linha">
          <div class="sobre-section-coluna">
            <!-- perguntas frequentes-->
            <section class="sobre" title="Perguntas Frequentes">
              <h2 class="section-titulo">f.a.q.</h2>

              <ul>
                <li class="servico-desc">
                  <h3 class="servico-titulo-hack">A participação é paga?</h3>Não. A participação do evento é gratuita. No entanto, os custos de
                  viagem, estadia e outros fora do evento são de responsabilidade do
                  participante.
                </li>

                <li class="servico-desc">
                  <h3 class="servico-titulo-hack">O evento é presencial ou online?</h3>O Hackathon é presencial. O nosso Q.G é na Av. Antônio Neudenir Benagna Micali,107 Taquaritinga-SP.
                </li>

                <li class="servico-desc">
                  <h3 class="servico-titulo-hack">Existe um limite de idade para participar?</h3>Sim. Uma vez que a nossa intenção é contratar novos profissionais talentosos, limitamos a participação apenas para pessoas com idade superior a 16 anos.
                </li>

                <li class="servico-desc">
                  <h3 class="servico-titulo-hack">Posso escolher minha equipe?</h3>Não. As equipes serão organizadas no dia na hora do evento. Valorizamos o trabalho em equipe independentemente de quem sejam os envolvidos.
                </li>
                <li class="servico-desc">
                  <h3
                    class="servico-titulo-hack"
                  >As esquipes serão compostas por quantos integrantes?</h3>As equipes terão entre 2 à 5 integrantes no máximo.
                </li>
                  <li class="servico-desc">
                  <h3
                    class="servico-titulo-hack"
                  >Ainda está com dúvidas?</h3>Fique a vontade para falar com a gente no e-mail doctype@suporte.com!
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
                <p
                  class="servico-desc"
                >Divulgação dos resultados e equipe vencedora. Não esqueça de verificar seu email!</p>
              </div>
            </div>
          </section>
        </div>
      </div>
    </section>
   
 <section class="sobre-section" title="Vencedores Hackathon 2018">
      <div class="interior-width">
        <!-- título -->
      
        <div class="sobre-section-linha">
          <div class="sobre-section-coluna">
            <!-- texto sobre a empresa -->
            <section class="sobre">
                <h2 class="section-titulo">{Vencedores 2018}</h2>
              <img class="time" src="../assets/grupohack.png" alt="">
            </section>
          </div>
          <section class="sobre-section-coluna" title="vídeo da empresa">
           <p>Venha fazer parte do nosso time você também!</p>
          </section>
        </div>
      </div>
    </section>
    <app-footer />
  </div>
</template>


<script>
import AppHeader from "../components/AppHeader";
import AppFooter from "../components/AppFooter";
export default {
  components: {
    AppHeader,
    AppFooter
  },

  data: () => ({
    valid: true,
    name: "",
    nameRules: [v => !!v || "Nome é necessário"],

    email: "",
    emailRules: [
      v => !!v || "E-mail é necessário",
      v => /.+@.+\..+/.test(v) || "E-mail Não Válido"
    ],
    select: null,
    items: ["Amazonas", "São Paulo", "Rio de Janeiro", "Rio Grande do Sul"],
    select: null,
    items2: ["Taquaritinga", "São Paulo", "Rio de Janeiro", "Santa Catarina"]
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
p {
  padding-top: 10px;
  /* font-weight: bold; */
}
h3 {
  color: #1e272e;
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

.time {
  height: 100%;
  margin-top: 15px;
  width: 600px;
  background-size: cover;
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