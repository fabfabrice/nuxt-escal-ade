<template>
  <div>
    <input id="burger" type="checkbox" />

    <label for="burger">
      <span></span>
      <span></span>
      <span></span>
    </label>

    <nav>
      <nuxt-link exact to="/">
        <img src="../static/img/logo.png" alt="logo" class="logoburger" />
      </nuxt-link>
      <ul id="dropdown">
        <li>
          <nuxt-link to="/actualites">Actualités</nuxt-link>
        </li>
        <!--
        -->
        <li>
          <nuxt-link to="/decrochage-scolaire">Décrochage scolaire</nuxt-link>
          <ul>
            <li>
              <nuxt-link to="/decrochage-scolaire#signes">Les premiers signes à repérer</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/decrochage-scolaire#vu">Le décrochage vu par les jeunes</nuxt-link>
            </li>
          </ul>
        </li>
        <!--
        -->
        <li>
          <nuxt-link to="/escal-ade">ESCAL'AdE</nuxt-link>
          <ul>
            <li>
              <nuxt-link to="/escal-ade#qui">Qui sommes-nous ?</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/escal-ade#projet">Notre projet</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/escal-ade#equipe">Notre équipe</nuxt-link>
            </li>
          </ul>
        </li>
        <!--
        -->
        <li>
          <nuxt-link to="/nos-actions">Nos actions</nuxt-link>
          <ul>
            <li>
              <nuxt-link to="/nos-actions#prevention">Prévention du décrochage scolaire</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/nos-actions#prise">Prise en charge du décrochage scolaire</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/nos-actions#formation">Formation et mutualisation des compétences</nuxt-link>
            </li>
          </ul>
        </li>
        <!--
        -->
        <li>
          <nuxt-link to="/ressources">Ressources</nuxt-link>
          <ul>
            <li>
              <nuxt-link to="/ressources#articles">Articles</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/ressources#bibliographie">Bibliographie</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/ressources#videos">Vidéos</nuxt-link>
            </li>
          </ul>
        </li>
        <li>
          <nuxt-link to="/adherer">Adhérer</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/faire-un-don">Faire un don</nuxt-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "app-mobile",
};
</script>

<style>
#dropdown > li:nth-child(1) {
  background-color: var(--red);
}
#dropdown > li:nth-child(2),
#dropdown > li:nth-child(2) ul {
  background-color: var(--blue);
}
#dropdown > li:nth-child(3),
#dropdown > li:nth-child(3) ul {
  background-color: var(--yellow);
}
#dropdown > li:nth-child(4),
#dropdown > li:nth-child(4) ul {
  background-color: var(--green);
}
#dropdown > li:nth-child(5),
#dropdown > li:nth-child(5) ul {
  background-color: var(--grey);
}
#dropdown > li:nth-child(6) {
  background-color: var(--orange);
}
#dropdown > li:nth-child(7) {
  background-color: var(--beige);
}

#dropdown a:hover {
  color: red;
}

#dropdown li > ul > li:last-child {
  padding-bottom: 1rem;
}

.logoburger {
  width: 6rem;
  padding: 0.2rem 0 0;
  margin: 0 5%;
}
input + label {
  position: fixed;
  top: 3%;
  right: 5.5%;
  height: 20px;
  width: 1.6rem;
  z-index: 5;
}
input + label span {
  position: absolute;
  width: 100%;
  height: 0.15rem;
  top: 50%;
  margin-top: -1px;
  left: 0;
  display: block;
  background: var(--font);
  transition: 0.5s;
}
input + label span:first-child {
  top: 3px;
}
input + label span:last-child {
  top: 16px;
}
label:hover {
  cursor: pointer;
}
input:checked + label span {
  opacity: 0;
  top: 50%;
}
input:checked + label span:first-child {
  opacity: 1;
  transform: rotate(405deg);
}
input:checked + label span:last-child {
  opacity: 1;
  transform: rotate(-405deg);
}
input ~ nav {
  background: white;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 4.3rem;
  z-index: 3;
  transition: 0.5s;
  transition-delay: 0.5s;
  overflow: hidden;
  border-bottom: 1px solid var(--font);
}
input ~ nav > ul {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
}
input ~ nav > ul > li {
  opacity: 0;
  transition: 0.5s;
  transition-delay: 0s;
}
input ~ nav > ul > li > a {
  text-decoration: none;
  text-transform: uppercase;
  color: var(--font);
  font-weight: 700;
  font-family: sans-serif;
  display: block;
  padding: 1rem 0 0.75rem;
}
input:checked ~ nav {
  height: 100%;
  transition-delay: 0s;
}
input:checked ~ nav > ul > li {
  opacity: 1;
  transition-delay: 0.5s;
}
@media screen and (min-width: 80rem) {
  input:checked,
  .logoburger,
  #dropdown,
  #burger {
    display: none;
  }
}
</style>