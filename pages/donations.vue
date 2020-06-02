<template>
  <div class="wrapper">
    <app-nav />
    <aside>
      <!-- <nav class="breadcrumb">
        <a href="#">Prévention du décrochage scolaire</a>
        <a href="#">Prise en charge du décrochage scolaire</a>
        <a href="#">Formation et partage de compétences</a>
      </nav>-->
    </aside>
    <main>
      <h1>Faire un don</h1>
      <section>
        <h2>Donations</h2>
        <p>Ici les prochains évènements</p>
        <app-article />
        <app-article />
        <app-article />
        <app-article />
        <app-article />
        <app-article />
        <a href="#" class="btn-bg">tous nos évènements</a>
      </section>
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppArticle from "~/components/AppArticle";

export default {
  components: {
    AppNav,
    AppArticle
  }
};
</script>

<style scoped>
.wrapper,
h1 {
  background-color: var(--beige);
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--beige);
  }
}
</style>

