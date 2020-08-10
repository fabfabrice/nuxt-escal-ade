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
      <h1>Ressources</h1>
      <section>
        <h2 id="articles">Articles</h2>
        <app-filter />
      </section>
      <section>
        <h2 id="bibliographie">Bibliographie</h2>
        <!-- modal et caroussel à combiner -->
      </section>
      <section>
        <h2 id="videos">Vidéos</h2>
        <article class="video">
          <figure>
            <iframe
              src="https://www.youtube.com/embed/dowqN2Z5EBE"
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
            <iframe
              src="https://www.youtube.com/embed/UMQEzHX8_98"
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
            <iframe
              src="https://www.youtube.com/embed/MMvzA5SfBGk"
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
            <iframe
              src="https://www.youtube.com/embed/FPFwqQ6CfUU"
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
            <iframe
              src="https://www.youtube.com/embed/LsmepvdW2xA"
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </figure>
        </article>
      </section>
      <app-footer />
    </main>
  </div>
</template>


<script>
import AppNav from "~/components/AppNav";
import AppFilter from "~/components/AppFilter";
import AppFooter from "~/components/AppFooter";
import AppMobile from "~/components/AppMobile";

export default {
  components: {
    AppNav,
    AppFilter,
    AppFooter,
    AppMobile,
  },
};
</script>

<style scoped>
.wrapper,
h1 {
  background-color: var(--grey);
}
main section {
  padding: 0;
}
.video figure iframe {
  padding: 0 1rem 1rem 1rem;
  margin-bottom: 1rem;
  max-width: 18rem;
  min-height: 18rem;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--grey);
  }
  main section {
    padding: 0 5rem;
  }
}
</style>
