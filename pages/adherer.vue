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
      <h1>Adhérer</h1>
      <section>
        <iframe
          src="https://docs.google.com/forms/d/e/1FAIpQLScjvYKs-czqvUQRU9Jme1BFs1_EQaIG66y9wE1N-cuUjGl8ww/viewform?embedded=true"
          width="100%"
          height="100%"
          frameborder="0"
          margin="0"
          marginwidth="0"
        >Loading...</iframe>
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
  background-color: var(--orange);
}
main section {
  height: 170vh;
  padding: 0 1rem;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--orange);
  }
}
</style>
