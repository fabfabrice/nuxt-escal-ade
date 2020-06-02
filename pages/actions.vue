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
      <h1>Nos actions</h1>
      <section>
        <h2>Prévention du décrochage scolaire</h2>
        <h3>Pourquoi se focaliser sur la prévention ?</h3>
        <app-number />
        <app-number>
          <template v-slot:number>2</template>
          <template
            v-slot:textnumber
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus eveniet ea sequi nobis odio architecto facilis repellat earum iste magnam.</template>
        </app-number>
        <app-number>
          <template v-slot:number>3</template>
          <template
            v-slot:textnumber
          >Lorem ipsum dolor sit olumurn ijoijioinioi alumnie doagrids repeokokllat novestrajie earum iste magnam.</template>
        </app-number>
        <img src="/img/actions/prise-en-charge3.png" alt />
        <article>
          <h3>La prévention au sein d'établissements scolaires</h3>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel nulla fugiat necessitatibus commodi harum itaque inventore explicabo aperiam veniam eius?</p>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel nulla fugiat necessitatibus commodi harum itaque inventore explicabo aperiam veniam eius?</p>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel nulla fugiat necessitatibus commodi harum itaque inventore explicabo aperiam veniam eius?</p>
        </article>
        <article>
          <h3>Nos actions en lien avec les établissements scolaires</h3>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel nulla fugiat necessitatibus commodi harum itaque inventore explicabo aperiam veniam eius?</p>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel nulla fugiat necessitatibus commodi harum itaque inventore explicabo aperiam veniam eius?</p>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel nulla fugiat necessitatibus commodi harum itaque inventore explicabo aperiam veniam eius?</p>
          <img src="/img/actions/prise-en-charge3.png" alt />
        </article>
      </section>
      <section>
        <h2>Prise en charge du décrochage scolaire</h2>
        <app-accordion
          v-for="(faq, i) in faqs"
          :faq="faq"
          :index="i"
          :key="i"
          :open="faq.open"
          @toggleOpen="toggleOpen"
        />
        <img src="/img/actions/prise-en-charge3.png" alt />
      </section>
      <section>
        <h2>Formation et partage de compétences</h2>
        <app-tab :tabs="tabs" :initialTab="initialTab">
          <template slot="tab-head-james">James</template>
          <template slot="tab-panel-james">
            <h4 class="title">James Potter</h4>
            <p class="description">
              James Potter is a young wizard who fought against Voldemort in the
              1970s, only to be killed along with his wife Lily while trying to
              protect their 15-month-old son Harry.
            </p>
            <p class="description">
              He was a descendant of Ignotus Peverell and the only child of wealthy,
              elderly parents.
            </p>
          </template>
          <template slot="tab-head-lily">Lily</template>
          <template slot="tab-panel-lily">
            <h4 class="title">Lily Potter</h4>
            <p class="description">
              Lily J. Potter was a Muggle-born witch, the younger daughter of Mr and
              Mrs Evans, and the younger sister of Petunia Evans.
            </p>
            <p class="description">
              She sacrificed herself to save Harry and caused Voldemort to loose the
              <strong>First Wizarding War</strong>.
            </p>
          </template>
          <template slot="tab-head-snape">Snape</template>
          <template slot="tab-panel-snape">
            <h4 class="title">no description needed</h4>
            <img
              class="image"
              src="https://media1.tenor.com/images/b58f4b6f5cc71fb1d9663c66d0b42cb7/tenor.gif"
              alt
            />
          </template>
        </app-tab>
        <img src="/img/actions/prise-en-charge3.png" alt />
      </section>
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppArticle from "~/components/AppArticle";
import AppNumber from "~/components/AppNumber";
import AppAccordion from "~/components/AppAccordion";
import AppTab from "~/components/AppTab";

export default {
  components: {
    AppNav,
    AppArticle,
    AppNumber,
    AppAccordion,
    AppTab
  },
  data() {
    return {
      initialTab: "james",
      tabs: ["james", "lily", "snape"],
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
  background-color: var(--green);
}
h3 {
  margin-bottom: 2rem;
  margin-top: 4rem;
}
h4 {
  color: var(--green);
  font-weight: 800;
}
.title {
  margin-top: 10px;
  margin-bottom: 20px;
}

.description {
  margin-top: 5px;
  max-width: 85%;
  line-height: 22px;
  margin-bottom: 10px;
}

.image {
  height: 160px;
  width: auto;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--green);
  }
}
</style>


