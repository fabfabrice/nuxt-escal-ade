<template>
  <ul id="menu">
    <li>
      <nuxt-link exact to="/">
        <img src="/img/logo.png" class="logo" alt />
      </nuxt-link>
    </li>
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
          <a href="#">Articles</a>
        </li>
        <li>
          <a href="#">Bibliographie</a>
        </li>
        <li>
          <a href="#">Vidéos</a>
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
</template>

<script>
export default {
  name: "app-nav",
};
</script>

<style>
/* GRID */

.logo {
  width: 50%;
}

#menu {
  display: none;
}

#menu li a {
  color: var(--font);
  font-size: 0.8rem;
}
#menu li {
  padding: 1.3rem 0;
}
#menu > li:nth-child(1) {
  background-color: var(--white);
  padding: 0.2rem;
}
#menu > li:nth-child(2) {
  background-color: var(--red);
}
#menu > li:nth-child(3),
#menu > li:nth-child(3) ul {
  background-color: var(--blue);
}
#menu > li:nth-child(4),
#menu > li:nth-child(4) ul {
  background-color: var(--yellow);
}
#menu > li:nth-child(5),
#menu > li:nth-child(5) ul {
  background-color: var(--green);
}
#menu > li:nth-child(6),
#menu > li:nth-child(6) ul {
  background-color: var(--grey);
}
#menu > li:nth-child(7) {
  background-color: var(--orange);
}
#menu > li:nth-child(8) {
  background-color: var(--beige);
}

/* MENU */
#menu,
#menu ul {
  padding: 0;
  margin: 0;
  list-style: none;
  text-align: center;
}
#menu li {
  display: inline-block;
  transition: 0.3s ease-in all;
}
#menu ul li {
  display: inherit;
}
#menu > li > ul {
  position: absolute;
  z-index: 1000;
  max-height: 0;
  top: 100%;
  left: 0;
  right: 0;
  padding: 0;
  overflow: hidden;
}
#menu > li:hover > ul {
  max-height: 60rem;
}

/* background links sub menu */
#menu li li {
  display: inline-block;
  width: 100%;
  vertical-align: top;
  height: 4.2rem;
}

/* the links */
#menu a {
  text-decoration: none;
}

#menu li:hover li a {
  color: var(--font);
}
#menu li:hover a,
#menu li li:hover a {
  color: red;
}

/* media queries */
@media screen and (min-width: 80rem) {
  #menu {
    display: grid;
    grid-template-columns: 12.5rem 1fr 14.5rem 1fr 1fr 1fr 1fr 12.5rem;
    text-align: center;
    text-transform: uppercase;
    font-weight: 800;
    position: fixed;
    width: 100%;
    z-index: 1000;
  }
}
</style>