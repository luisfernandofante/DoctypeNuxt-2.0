<template>
<div>
    <!-- cabeçalho -->
    <app-header />
    <section class="contato-section" title="Contato">
      <div class="meio-width">
        <h2 class="section-titulo">{Contato}</h2>
        <p>Nosso suporte "Patrício, o Ornitorrinco" ficará muito feliz em te ajudar!</p>
             <img  class="patricio" src="../assets/platypus.svg" alt="ícone de um ornitorrinco">
        <input type="text" class="name" placeholder="Nome" title="nome">
        <input type="email" class="email" placeholder="Email" title="email">
        <textarea rows="1" placeholder="Messagem" class="message" title="menssagem"></textarea>
        <button title="enviar">Enviar</button>
  
      </div>
    </section>
    
   <app-footer/>
</div>
</template>

<script>
import AppHeader from "../components/AppHeader";
import AppFooter from "../components/AppFooter";
export default {
    components:{
        AppFooter,AppHeader,
    }
};
</script>

<style scoped>
 h2::after {
            content:'|';
            opacity: 1;
            display: inline-block;
            animation: pisca .7s infinite;
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