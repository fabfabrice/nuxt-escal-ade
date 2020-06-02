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
      <h1>Décrochage scolaire</h1>
      <section>
        <h2>Les premiers signes à repérer</h2>
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
        <h2>Le décrochage vu par les jeunes</h2>
        <app-testimony />
        <app-testimony>
          <template
            v-slot:textquote
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus nihil velit voluptate accusantium aperiam quisquam nemo nam tenetur debitis at ab repudiandae, vero voluptates dolorem, explicabo fuga veniam quaerat, rem ea cum maiores? Pariatur doloremque aperiam sint ut! Aspernatur, doloribus vero! Maxime fuga nemo in obcaecati quos doloremque voluptate, ducimus dignissimos totam eos! Iure quasi quae temporibus nihil corrupti fugit, doloremque possimus ad. Eligendi ex id non maxime aliquid neque exercitationem commodi illo. Velit ab, iure aliquam culpa vero fugiat in quis laudantium, facilis minus repudiandae. Odit aperiam eveniet pariatur deserunt amet nostrum recusandae. Aspernatur architecto minus facere illum eius?</template>
          <template v-slot:author>Patrick</template>
        </app-testimony>
      </section>
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppAccordion from "~/components/AppAccordion";
import AppTestimony from "~/components/AppTestimony";

export default {
  components: {
    AppNav,
    AppAccordion,
    AppTestimony
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
  background-color: var(--blue);
}
h2::before,
h2::after {
  content: "";
  flex: 1;
  border-bottom: 1rem solid var(--blue);
}
</style>
