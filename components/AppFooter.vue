<template>
  <div>
    <footer class="flex-rw">
      <!-- seção de icones -->
      <section class="footer-social-section flex-rw">
        <!-- texto -->
        <!-- <span class="footer-social-overlap footer-social-connect">
                SIGA A &lt;!DOCTYPE&gt;
        </span>-->
        <!-- final do texto -->
        <!-- icones -->
        <span class="footer-social-overlap footer-social-icons-wrapper">
          <a
            href="https://behance.com"
            class="generic-anchor behance"
            target="_blank"
            title="Behance"
          >
            <i class="fab fa-behance-square"></i>
          </a>
          <a
            href="https://www.facebook.com"
            class="generic-anchor facebook"
            target="_blank"
            title="Facebook"
          >
            <i class="fab fa-facebook-square"></i>
          </a>
          <a href="http://github.com" class="generic-anchor github" target="_blank" title="Github">
            <i class="fab fa-github-square"></i>
          </a>
          <a
            href="https://www.twitter.com"
            class="generic-anchor twitter"
            target="_blank"
            title="Twitter"
          >
            <i class="fab fa-twitter-square"></i>
          </a>
        </span>
        <!-- final dos ícones -->
      </section>
      <!-- final da seção de icones -->

      <!-- últimas informações -->
      <section class="footer-bottom-section flex-rw">
        <div class="footer-bottom-wrapper">
          <i class="fa fa-copyright" role="copyright" alt="ícone de direitos autorais"></i> 2019 All Rights Reserved.
          <address class="footer-address" role="company address">
            &lt;!DOCTYPE&gt; Av. Antonio Neudenir Benagna Micali,107.Taquaritinga-SP
            Tel:(16)99166-2578
          </address>
        </div>
      </section>
      <!-- final das últimas informações -->
    </footer>
    <!-- final do footer -->
  </div>
</template>
<style  scoped>
html,
body {
  height: 100%;
}

body {
  margin: auto;
  display: flex;
  flex-flow: column nowrap;
  font-family: "Space Mono", monospace;
  justify-content: space-between;
}

a {
  text-decoration: none;
}

.generic-anchor {
  color: white;
}
.facebook:hover {
  color: #487eb0;
}
.twitter:hover {
  color: #22a6b3;
}
.github:hover {
  color: #6c5ce7;
}
.behance:hover {
  color: #0097e6;
}

.flex-rw {
  display: flex;
  flex-flow: row wrap;
}

footer {
  background: black;
  margin-top: auto;
  width: 100%;
}
.footer-social-icons-wrapper {
  line-height: 53%;
}
.footer-social-section {
  width: 100%;
  align-items: center;
  justify-content: space-around;
  /* position: relative; */
  margin-top: 5px;
}

.footer-social-overlap {
  position: relative;
  background-color: black;
}

.footer-social-connect {
  font: 3.5rem;
  color: #fff;
}

.footer-social-overlap > a {
  font-size: 2em;
}

.footer-bottom-section {
  width: 100%;
  padding: 10px;
  border-top: 1px solid #ccc;
  margin-top: 10px;
}

.footer-bottom-wrapper {
  font-size: 1rem;
  color: #fff;
  align-items: center;
  text-align: justify;
}

.footer-social-overlap > a:not(:first-child) {
  margin-left: 10px;
}

.footer-address {
  display: inline;
  font-style: normal;
}

@media screen and (min-width: 568px) {
  .footer-social-overlap > a {
    font-size: 2.5rem;
  }

  .footer-social-overlap {
    display: flex;
    justify-content: center;
  }

  .footer-bottom-section {
    padding: 0 5px 10px 5px;
  }
  .footer-bottom-wrapper {
    text-align: center;
    width: 100%;
    margin-top: 10px;
    font-size: 1.2rem;
  }
}
</style>