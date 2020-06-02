<template>
  <div class="wrapper">
    <header>
      <app-nav />
      <section class="hero">
        <h1 class="slogan">
          <span>Prévention</span>
          <span>Prise en charge</span>
          <span>Décrochage scolaire</span>
        </h1>
        <a href="#" class="btn-bg">en savoir plus</a>
      </section>
    </header>
    <aside>
      <!-- <nav class="breadcrumb">
        <a href="#">Prévention du décrochage scolaire</a>
        <a href="#">Prise en charge du décrochage scolaire</a>
        <a href="#">Formation et partage de compétences</a>
      </nav>-->
    </aside>
    <main>
      <section>
        <h2>Actualité</h2>
        <p>Ici les prochains évènements</p>
        <app-article />
        <app-article />
        <a href="#" class="btn-bg">tous nos évènements</a>
      </section>
      <section>
        <h2>Décrochage scolaire</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora
          facilis debitis veniam asperiores! Quam, unde, ex ea voluptatem
          nobis expedita delectus voluptatibus voluptas obcaecati quos
          adipisci maxime officiis animi quod.
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit harum
          blanditiis vitae, consequuntur molestiae ipsam.
        </p>
        <a href="#" class="btn-bg">en savoir plus</a>
      </section>
      <section>
        <h2>à propos de l'association</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora
          facilis debitis veniam asperiores! Quam, unde, ex ea voluptatem
          nobis expedita delectus voluptatibus voluptas obcaecati quos
          adipisci maxime officiis animi quod.
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit harum
          blanditiis vitae, consequuntur molestiae ipsam.
        </p>
        <iframe
          scrolling="no"
          id="hearthis_at_track_1630205"
          width="100%"
          height="150"
          src="https://app.hearthis.at/embed/1630205/transparent_black/?hcolor=&color=&style=2&block_size=2&block_space=1&background=1&waveform=0&cover=0&autoplay=0&css="
          frameborder="0"
          allowtransparency
          allow="autoplay"
        >
          <p>
            Listen to
            <a
              href="https://hearthis.at/marmitefm884/portrait-nassira-mohamad-oct17/"
              target="_blank"
            >Portrait : Nassira Mohamad - Octobre 2017</a>
            <span>by</span>
            <a href="https://hearthis.at/marmitefm884/" target="_blank">Marmite FM 88.4</a>
            <span>on</span>
            <a href="https://hearthis.at/" target="_blank">hearthis.at</a>
          </p>
        </iframe>
        <a href="#" class="btn-bg">en savoir plus</a>
      </section>
      <section>
        <h2>Prévention et accompagnement</h2>
        <img src="/img/actions/prise-en-charge3.png" alt />
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit harum
          blanditiis vitae, consequuntur molestiae ipsam.
        </p>
        <a href="#" class="btn-bg">en savoir plus</a>
      </section>
      <!--⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙  ADHERER  ⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙-->
      <section>
        <h2>Adhérer</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fugit
          tempore perspiciatis vero obcaecati sunt perferendis?
        </p>
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

<style>
.wrapper {
  display: grid;
  grid-template-columns: 5% auto 5%;
  grid-template-areas:
    "head head head"
    ". main .";
}
header {
  grid-area: head;
  background: url(/img/home-background.png) center fixed;
  background-size: cover;
  height: 100vh;
  z-index: 1000;
}

header section {
  text-align: center;
}
.breadcrumb {
  display: none;
}
main {
  grid-area: main;
  text-align: center;
  background: #fff;
}
main section {
  padding: 0 1rem;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    content: "";
    flex: 1;
    border-bottom: 1rem solid var(--white);
  }
}
@media screen and (min-width: 80rem) {
  .wrapper {
    grid-template-columns: 12.5rem 1fr 12.5rem;
    grid-template-areas:
      "head head head"
      "aside main .";
    background: var(--white);
  }
  main {
    text-align: left;
  }
  main section {
    padding: 0 5rem;
  }
  aside {
    grid-area: aside;
  }
  .breadcrumb {
    display: block;
    position: fixed;
    padding: 1rem;
    top: 24%;
    left: 1%;
    font-weight: 800;
  }
  .breadcrumb a {
    color: var(--font);
    display: block;
    padding: 2rem 0;
    max-width: 10rem;
    border-bottom: 1px solid var(--display);
  }
  .breadcrumb a:first-child {
    color: var(--display);
    text-decoration: underline;
    letter-spacing: var(--spacing);
  }
}
</style>

