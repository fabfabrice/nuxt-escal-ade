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
      <h1>Escal'ade</h1>
      <section>
        <h2>Qui sommes-nous ?</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus velit recusandae assumenda voluptate a commodi.</p>
        <app-quote />
      </section>
      <section>
        <h2>Notre projet</h2>
        <h3>La genèse de notre projet</h3>
        <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cum dolores ipsum harum voluptas in aperiam ullam est? Totam, enim consequatur!</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae quis explicabo esse deserunt quas veritatis quibusdam, tempore omnis fuga doloremque distinctio cupiditate quidem et sint maiores. Esse earum soluta mollitia laborum quos! Dolore excepturi cumque ipsam delectus repellat quae fugit!</p>
        <h3>Nos valeurs</h3>
        <!-- ajouter cercle avec valeurs -->
        <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Officia quasi aliquid quaerat similique distinctio ullam maiores perspiciatis alias molestiae explicabo commodi aperiam cupiditate repudiandae corporis architecto provident, facilis, voluptatibus ratione!</p>
        <h3>Nos partenaires</h3>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Enim blanditiis, aliquam corporis a reiciendis commodi quos reprehenderit sapiente rerum dolore nihil itaque magnam numquam. Repellat est numquam dolorum sed nihil.</p>
      </section>
      <section>
        <h2>Notre équipe</h2>
        <app-accordion
          v-for="(faq, i) in faqs"
          :faq="faq"
          :index="i"
          :key="i"
          :open="faq.open"
          @toggleOpen="toggleOpen"
        />
      </section>
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppQuote from "~/components/AppQuote";
import AppAccordion from "~/components/AppAccordion";

export default {
  components: {
    AppNav,
    AppQuote,
    AppAccordion
  },
  data() {
    return {
      faqs: [
        {
          question: "Who is the best Superhero?",
          answer: "I'm not sure but we love him 3000",
          open: false
        },
        {
          question: "What is Goku's form called with White Hair?",
          answer: "Mastered Ultra Instinct",
          open: false
        },
        {
          question: "Have you liked & subscried yet?",
          answer: "YES",
          open: false
        }
      ]
    };
  },
  methods: {
    toggleOpen: function(index) {
      this.faqs = this.faqs.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open;
        } else {
          faq.open = false;
        }

        return faq;
      });
    }
  }
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
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--yellow);
  }
}
</style>

