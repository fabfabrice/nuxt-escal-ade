<template>
  <div class="wrapper">
    <app-nav />
    <aside>
      <nav class="breadcrumb">
        <a href="#">Prévention du décrochage scolaire</a>
        <a href="#">Prise en charge du décrochage scolaire</a>
        <a href="#">Formation et partage de compétences</a>
      </nav>
    </aside>
    <main>
      <h1>Ressources</h1>
      <section>
        <h2>Articles</h2>
        <app-filter />
      </section>
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppFilter from "~/components/AppFilter";

export default {
  components: {
    AppNav,
    AppFilter
  }
};
</script>

<style scoped>
.wrapper,
h1 {
  background-color: var(--grey);
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--grey);
  }
}
</style>

