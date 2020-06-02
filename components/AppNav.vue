<template>
  <ul id="menu">
    <li>
      <nuxt-link exact to="/">Home</nuxt-link>
    </li>
    <li>
      <nuxt-link to="/actu">Actualités</nuxt-link>
    </li>
    <!--
    -->
    <li>
      <nuxt-link to="/decrochage">Décrochage scolaire</nuxt-link>
      <ul>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
      </ul>
    </li>
    <!--
    -->
    <li>
      <nuxt-link to="/escal-ade">ESCAL'AdE</nuxt-link>
      <ul>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
      </ul>
    </li>
    <!--
    -->
    <li>
      <nuxt-link to="/actions">Nos actions</nuxt-link>
      <ul>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
      </ul>
    </li>
    <!--
    -->
    <li>
      <nuxt-link to="/ressources">Ressources</nuxt-link>
      <ul>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
        <li>
          <a href="#">lien sous menu 3</a>
        </li>
      </ul>
    </li>
    <li>
      <nuxt-link to="/adherer">Adhérer</nuxt-link>
    </li>
    <li>
      <nuxt-link to="/donations">Faire un don</nuxt-link>
    </li>
  </ul>
</template>

<script>
export default {
  name: "app-nav"
};
</script>

<style>
/* GRID */

#menu {
  display: none;
}

#menu li a {
  color: var(--font);
  font-size: 0.8rem;
}
#menu li {
  padding: 1.2rem 0;
}
#menu > li:nth-child(1) {
  background-color: var(--white);
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
  width: 34%;
  vertical-align: top;
  height: 4rem;
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