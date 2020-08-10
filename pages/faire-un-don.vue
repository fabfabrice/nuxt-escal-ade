<template>
  <div class="wrapper">
    <app-mobile />
    <app-nav />
    <!-- <aside>
      <nav class="breadcrumb">
        <a href="#">Prévention du décrochage scolaire</a>
        <a href="#">Prise en charge du décrochage scolaire</a>
        <a href="#">Formation et partage de compétences</a>
      </nav>
    </aside>-->
    <main>
      <h1>Faire un don</h1>
      <section>
        <h2>Donations</h2>
        <p>Page en construction</p>
      </section>
      <app-footer />
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppArticle from "~/components/AppArticle";
import AppFooter from "~/components/AppFooter";
import AppMobile from "~/components/AppMobile";

export default {
  components: {
    AppNav,
    AppArticle,
    AppFooter,
    AppMobile,
  },
};
</script>

<style scoped>
.wrapper,
h1 {
  background-color: var(--beige);
}
main section {
  min-height: 63vh;
  padding: 0 1rem;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--beige);
  }
  main section {
    padding: 0 5rem;
  }
}
</style>
