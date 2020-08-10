<template>
  <div class="wrapper">
    <header>
      <app-mobile />
      <app-nav />
      <section class="hero">
        <h1 class="slogan">
          <span>Prévention</span>
          <span>Prise en charge</span>
          <span>Décrochage scolaire</span>
        </h1>
        <nuxt-link to="/nos-actions" class="btn-bg" id="green">En savoir plus</nuxt-link>
      </section>
    </header>
    <main>
      <section>
        <h2>Actualités</h2>
        <p>Pas d'évènements à venir</p>
        <!-- <figure class="actu">
          <img src="/img/actu/actu-forum2019.jpg" alt="actu" />
          <figcaption>
            <h3>Forum des associations</h3>
            <h4>samedi 7 septembre 2019</h4>
            <p>ESCAL'AdE sera présente au forum des associations 2019 au gymnase Broustal à Trappes, 6 avenue Ludwig Van Beethoven</p>
          </figcaption>
        </figure>-->
        <nuxt-link to="/actualites" class="btn-bg" id="red">Tous nos évènements</nuxt-link>
      </section>
      <section>
        <h2>Qui sont les décrocheurs scolaires ?</h2>
        <p>
          Officiellement un décrocheur scolaire est un élève qui n’obtient ni
          diplôme ni qualification à l’issue d’une année scolaire. De plus, il
          n’est pas inscrit l’année suivante dans une formation générale ou
          professionnelle.
        </p>
        <p>
          Le décrochage scolaire est la rencontre de plusieurs facteurs à un
          moment donnée de la scolarité de l’élève. Il peut être dû à la fois à
          des facteurs individuels tels que l’absentéisme, le comportement, les
          résultats scolaires, la santé mentale de l’élève, et à des facteurs
          environnementaux tels que le climat scolaire, la dynamique familiale
          et culturelle, ou des facteurs socio-économiques.
        </p>
        <nuxt-link to="/decrochage-scolaire" class="btn-bg" id="blue">En savoir plus</nuxt-link>
      </section>
      <section>
        <h2>Quelle aide apportons-nous ?</h2>
        <p>
          L’association ESCAL'AdE accompagne les enfants, les adolescents et les
          jeunes adultes en décrochage scolaire ou en voie de décrochage, pour
          qu’ils tendent vers un parcours de vie qui soit au plus près de leurs
          aspirations. Nous proposons aussi des actions destinées aux familles
          et aux professionnels afin qu’ils soient les premiers acteurs de la
          lutte contre le décrochage scolaire.
        </p>
        <video controls="controls">
          <source src="videos/video-alma.mp4" type="video/mp4" />
          <source src="videos/video-alma.webm" type="video/webm" />
          <source src="videos/video-alma.ogv" type="video/ogg" />Ici l'alternative à la vidéo : un lien de téléchargement, un message,
          etc.
        </video>
        <p style="font-style:italic">
          Nassira Mohammad, co-fondatrice de l’association, présente sur marmite
          FM, décrit quelques éléments essentiels des actions de l’association
          lors du forum de rentrée 2018.
        </p>
        <nuxt-link to="/escal-ade" class="btn-bg" id="yellow">En savoir plus</nuxt-link>
      </section>
      <!--⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙  ADHERER  ⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙⁙-->
      <section>
        <h2>Adhérer</h2>
        <p>
          Vous êtes élèves, parents, professionnels de l’éducation, ou si tout
          simplement vous souhaitez devenir bénévole, vous pouvez adhérer à
          l’association et participer à la lutte contre le décrochage scolaire.
        </p>
        <nuxt-link to="/nos-actions" class="btn-bg" id="orange">Adhérer</nuxt-link>
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
  background: url(/img/test-bg.png) center fixed;
  background-size: cover;
  height: 100vh;
  z-index: 1000;
}

.yellow {
  color: yellow;
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
/* main section {
  padding: 0 1rem;
} */
.actu {
  padding: 0 0 1rem;
}
#yellow {
  background-color: var(--yellow);
}
#yellow:hover {
  background-color: var(--yellow-hover);
}
#green {
  background-color: var(--green);
}
#green:hover {
  background-color: var(--green-hover);
}
#blue {
  background-color: var(--blue);
}
#blue:hover {
  background-color: var(--blue-hover);
}
#red {
  background-color: var(--red);
}
#red:hover {
  background-color: var(--red-hover);
}
#orange {
  background-color: var(--orange);
}
#orange:hover {
  background-color: var(--orange-hover);
}
video {
  max-width: 18rem;
  min-height: 18rem;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    content: "";
    flex: 1;
    border-bottom: 1rem solid var(--white);
  }
  main section {
    padding: 0 5rem;
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
  aside {
    grid-area: aside;
  }
  .actu {
    display: flex;
  }
  .actu img {
    max-width: 23%;
  }
  .actu figcaption {
    padding-left: 3.5rem;
  }
}
</style>
