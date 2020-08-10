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
      <h1>Escal'ade</h1>
      <section>
        <h2 id="qui">Qui sommes-nous ?</h2>
        <p>
          Nous sommes une association de prévention et de prise en charge du
          décrochage scolaire. Nous menons des actions directes et indirectes de
          lutte contre le décrochage ayant pour axe principal le développement
          et le bien être psychologique des enfants, des adolescents, des jeunes
          adultes, des familles et des professionnels de l’éducation.
        </p>
      </section>
      <section>
        <h2 id="projet">Notre projet</h2>
        <h3>La genèse de notre projet</h3>
        <p>
          Nous sommes une association loi de 1901 créée en 2013 à la suite d’une
          expérience de 3 ans réalisée au sein d’un lycée professionnel
          présentant un taux de décrochage important.
        </p>
        <p>
          Cette expérience proposait de dédier un accompagnement psychologique
          spécifique aux décrocheurs scolaires pour prévenir et prendre en
          charge le décrochage scolaire interne à l’établissement, et ainsi
          compléter d’autres actions pluridisciplinaires déjà proposées par les
          professionnels des établissements.
        </p>
        <h3>Nos valeurs</h3>
        <!-- ajouter cercle avec valeurs -->
        <app-quote />
        <!-- <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Officia quasi aliquid quaerat similique distinctio ullam maiores perspiciatis alias molestiae explicabo commodi aperiam cupiditate repudiandae corporis architecto provident, facilis, voluptatibus ratione!</p> -->
        <h3>Nos partenaires</h3>
        <article class="partenaires">
          <div>
            <img src="/img/escal-ade/partenaire1.png" alt />
            <p>Médiathèque Anatole France</p>
          </div>
          <div>
            <img src="/img/escal-ade/partenaire2.png" alt />
            <p>CGET</p>
          </div>
          <div>
            <img src="/img/escal-ade/partenaire3.png" alt />
            <p>Assemblée Nationale</p>
          </div>
          <div>
            <img src="/img/escal-ade/partenaire4.png" alt />
            <p>
              Direction régionale de la Jeunesse, des Sports et de la Cohésion
              sociale
            </p>
          </div>
        </article>
      </section>
      <section>
        <h2 id="equipe">Notre équipe</h2>
        <app-accordion
          v-for="(faq, i) in faqs"
          :faq="faq"
          :index="i"
          :key="i"
          :open="faq.open"
          @toggleOpen="toggleOpen"
        />
      </section>
      <app-footer />
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppQuote from "~/components/AppQuote";
import AppAccordion from "~/components/AppAccordion";
import AppFooter from "~/components/AppFooter";
import AppMobile from "~/components/AppMobile";

export default {
  components: {
    AppNav,
    AppQuote,
    AppAccordion,
    AppFooter,
    AppMobile,
  },
  data() {
    return {
      faqs: [
        {
          question: "Nassira Mohamad",
          answer:
            "Directrice Générale de l'Association, psychologue pour Enfants et Adolescents",
          open: true,
        },
        {
          question: "Thayib Mohamad",
          answer: "Président de l'Association",
          open: false,
        },
        {
          question: "Brigitte Cheddad",
          answer: "Trésorière",
          open: false,
        },
        {
          question: "Françoise Croquet",
          answer:
            "Secrétaire de l'Association, en charge des courriers, de la rédaction de documents ainsi que de la gestion et des compte-rendus des réunions",
          open: false,
        },
        {
          question: "Florian Viéville",
          answer: "Webdesigner et développeur web",
          open: false,
        },
        {
          question: "Mélanie Sordon",
          answer: "Psychologue pour enfants et adolescents",
          open: false,
        },
        {
          question: "Marie Lecuyer",
          answer: "Educatrice",
          open: false,
        },
        {
          question: "Audrey Serrier",
          answer: "Comptable, conseils",
          open: false,
        },
        {
          question: "Marie-Laure Testaud",
          answer: "Avocate, conseils",
          open: false,
        },
      ],
    };
  },
  methods: {
    toggleOpen: function (index) {
      this.faqs = this.faqs.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open;
        } else {
          faq.open = false;
        }

        return faq;
      });
    },
  },
};
</script>

<style scoped>
.wrapper,
h1 {
  background-color: var(--yellow);
}
h3 {
  margin-bottom: 2rem;
}
h3:not(:first-child) {
  margin-top: 4rem;
}
main section {
  padding: 0 1rem;
}
.partenaires {
  display: flex;
  flex-direction: column;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--yellow);
  }
  .partenaires {
    flex-wrap: wrap;
    flex-direction: row;
  }
  .partenaires div {
    width: 25%;
    padding: 0 1.5rem 0 0;
  }
  main section {
    padding: 0 5rem;
  }
}
</style>
