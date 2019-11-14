<template>
  <div>
    <header>
      <nav>
        <a href="/">
          <img
            class="logo"
            src="../assets/logo_doctype.svg"
            alt="logotipo da empresa Doctype"
            title="<!DOCTYPE>"
          />
        </a>

        <input type="checkbox" id="chk" />
        <label for="chk" class="mostra-menu-btn">
       <v-icon large>mdi-menu</v-icon>
        </label>

        <ul class="menu">
          <a href="/" title="Início">Início</a>
          <a href="/pacotes" title="Pacotes">Pacotes</a>
          <a href="/hackathon" title="Hackathon">Hackathon</a>
          <a href="/sobre" title="Sobre">Sobre</a>
          <a href="/contato" title="Contato">Contato</a>
          <a href="admin/login" title="Login">Login</a>
          <label for="chk" class="esconde-menu-btn">
            <v-icon large>mdi-close</v-icon>
          </label>
        </ul>
      </nav>
    </header>
  </div>
</template>

<style scoped>

header {
  height: 100px;
  background: black;
  padding: 0 20px;

  display: flex;
}

nav {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.logo {
  line-height: 100px;
  justify-content: left;
  height: 100%;
  width: 90px;
}

.menu {
  line-height: 100px;
}
.menu a {
  color:white;
  text-transform: uppercase;
  text-decoration: none;
  padding: 0 10px;
  transition: 0.4s;

}
.menu a:hover{
 text-decoration: line-through;
}

.mostra-menu-btn,
.esconde-menu-btn {
  transition: 0.4s;
  font-size: 30px;
  cursor: pointer;
  display: none;
}
/* .mostra-menu-btn {
  float: right;
} */
.esconde-menu-btn .v-icon {
  line-height: 100px;
}

#chk {
  position: absolute;
  visibility: hidden;
  z-index: -1111;
}

@media screen and (max-width: 800px) {
  .mostra-menu-btn,
  .esconde-menu-btn {
    display: flex;
  }
  .menu {
    z-index: 2;
    position: absolute;
    width: 100%;
    height: 500px;
    background: black;
    right: -100%;
    top: 0;
    text-align: center;
    padding: 70px 0;
    line-height: normal;
    transition: 0.7s;
  }
  .menu a {
    display: block;
    padding: 25px;
   
  }
 .v-icon{
   color:white;
   
 }
  .esconde-menu-btn {
    position: absolute;
    top: 5px;
    right: 15px;
  }
  #chk:checked ~ .menu {
    right: 0;
  }

  .v-parallax {
    position: relative;
    z-index: -12000;
  }
}
</style>