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
      <h1>Décrochage scolaire</h1>
      <section>
        <h2 id="signes">Les premiers signes à repérer</h2>
        <app-accordion
          v-for="(faq, i) in faqs"
          :faq="faq"
          :index="i"
          :key="i"
          :open="faq.open"
          @toggleOpen="toggleOpen"
        />
      </section>
      <section>
        <h2 id="vu">Le décrochage vu par les jeunes</h2>
        <!-- <app-testimony />
        <app-testimony>
          <template
            v-slot:textquote
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus nihil velit voluptate accusantium aperiam quisquam nemo nam tenetur debitis at ab repudiandae, vero voluptates dolorem, explicabo fuga veniam quaerat, rem ea cum maiores? Pariatur doloremque aperiam sint ut! Aspernatur, doloribus vero! Maxime fuga nemo in obcaecati quos doloremque voluptate, ducimus dignissimos totam eos! Iure quasi quae temporibus nihil corrupti fugit, doloremque possimus ad. Eligendi ex id non maxime aliquid neque exercitationem commodi illo. Velit ab, iure aliquam culpa vero fugiat in quis laudantium, facilis minus repudiandae. Odit aperiam eveniet pariatur deserunt amet nostrum recusandae. Aspernatur architecto minus facere illum eius?</template>
          <template v-slot:author>Patrick</template>
        </app-testimony>-->
        <p>Mise à jour en cours</p>
      </section>
      <app-footer />
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppAccordion from "~/components/AppAccordion";
import AppTestimony from "~/components/AppTestimony";
import AppFooter from "~/components/AppFooter";
import AppMobile from "~/components/AppMobile";

export default {
  components: {
    AppNav,
    AppAccordion,
    AppTestimony,
    AppFooter,
    AppMobile,
  },
  data() {
    return {
      faqs: [
        {
          question: "L'absentéisme scolaire",
          answer:
            "L’absentéisme chez l’élève peut provoquer à la fois des lacunes concernant les apprentissages théoriques d’autant plus si l’élève n’est pas autonome dans ces apprentissages. Un absentéisme perlé n’est pas suffisant pour qualifier un élève de décrocheur. Cet absentéisme doit à la fois perdurer dans le temps mais aussi avoir un impact sur d’autres domaines scolaires.",
          open: false,
        },
        {
          question: "Le comportement",
          answer:
            "Un comportement inadapté aux attentes de l’école sans forcément parlé de troubles peut aussi entraîner un décrochage scolaire lorsqu’il ne permet pas de recevoir les savoirs et les savoir faire transmis par l’école.",
          open: false,
        },
        {
          question: "Les performances scolaires",
          answer:
            "Les performances scolaires quant à elles sont le signe de décrochage le plus sanctionné à la fois par le corps enseignant mais aussi par les parents. Elles déterminent de façon parfois « injuste » l’orientation des élèves qui subissent ainsi un parcours non choisi.",
          open: false,
        },
        {
          question: "Motivation / investissement",
          answer:
            "La motivation et l’investissement sont le signe de décrochage scolaire le moins bien identifié car ce critère dépend de la subjectivité de l’observateur (enseignant ou parent par exemple), et de la manière dont l’élève va l’exprimer. De plus, le type de motivation est différent en fonction de chaque élève.",
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
  background-color: var(--blue);
}
h2::before,
h2::after {
  content: "";
  flex: 1;
  border-bottom: 1rem solid var(--blue);
}
main section {
  padding: 0 1rem;
}
@media screen and (min-width: 45rem) {
  main section {
    padding: 0 5rem;
  }
}
</style>
