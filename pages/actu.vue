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
      <h1>Actualités</h1>
      <section>
        <h2>Actualités</h2>
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
  background-color: var(--red);
}
h2::before,
h2::after {
  content: "";
  flex: 1;
  border-bottom: 1rem solid var(--red);
}
</style>

