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
      <h1>Nos actions</h1>
      <section>
        <h2 id="prevention">Prévention du décrochage scolaire</h2>
        <h3>Pourquoi la prévention est-elle importante ?</h3>
        <app-number>
          <template v-slot:number>1</template>
          <template
            v-slot:textnumber
          >Plus tôt sont repérés les premiers signes de décrochage, plus l’élève a de chances de raccrocher à un parcours scolaire stable.</template>
        </app-number>
        <app-number>
          <template v-slot:number>2</template>
          <template
            v-slot:textnumber
          >Plus tôt est pris en charge le processus de décrochage moins il est nécessaire de solliciter de professionnels.</template>
        </app-number>
        <app-number>
          <template v-slot:number>3</template>
          <template
            v-slot:textnumber
          >Plus tôt on accompagne le décrocheur scolaire dans son processus de raccrochage, plus l’élève a de chances de bénéficier d’un raccrochage durable.</template>
        </app-number>
        <img src="/img/actions/prise.svg" alt />
        <article>
          <h3>La prévention au sein d'établissements scolaires</h3>
          <p>Elle est mise en place par des professionnels de l’éducations : psychologues, assistantes sociales, infirmières scolaires, assistants d’éducation, professeurs et chefs d’établissement.</p>
          <p>Elle sollicite parfois des professionnels extérieurs tels que éducateurs, conseillers d’orientation psychologue, médiateurs, professionnels de santé ou de justice, et des psychologues.</p>
          <p>Afin de repérer le plus tôt possible les premiers signes d’un processus de décrochage, des bilans pluridisciplinaires sont proposés par les professionnels de l’association, permettant ainsi d'évaluer les différents facteurs tels que l’absentéisme, les difficultés de comportement. les basses performances scolaires, et la motivation.</p>
        </article>
        <article>
          <h3>Comment bénéficier de nos actions ?</h3>
          <p>
            Qui fait appel à nous ?
            <br />Les demandes d’accompagnement peuvent être à la demande à la fois de l’élève ou de sa famille, mais aussi des établissements scolaires, des cabinets médicaux ou d’autres structures médico socio éducatives.
          </p>
          <p>
            Comment procéder ?
            <br />Les demandes d’accompagnement peuvent être à la demande à la fois de l’élève ou de sa famille, mais aussi des établissements scolaires, des cabinets médicaux ou d’autres structures médico socio éducatives.
          </p>
          <p>Après validation de votre dossier, vous serez contacté par un professionnel de l’association afin de fixer un premier rendez-vous.</p>
          <img src="/img/actions/illus.svg" alt />
        </article>
      </section>
      <section>
        <h2 id="prise">Prise en charge du décrochage scolaire</h2>
        <h3>Où ?</h3>
        <app-accordion
          v-for="(faq, i) in where"
          :faq="faq"
          :index="i"
          :key="i"
          :open="faq.open"
          @toggleOpen="toggleOpen"
        />
        <h3>Comment ?</h3>
        <p>Afin d’observer au plus près les difficultés des jeunes décrocheurs, nous mettons en place une prise en charge tridimentionnelle qui prend en compte à la fois les aspects individuels, groupaux et institutionnel des processus de décrochage.</p>
        <app-accordion
          v-for="(faq, i) in how"
          :faq="faq"
          :index="i"
          :key="i"
          :open="faq.open"
          @toggleOpen="toggleOpen"
        />
        <img src="/img/actions/mental.svg" alt />
      </section>
      <section>
        <h2 id="formation">Formation / mutualisation des compétences</h2>
        <app-tab :tabs="tabs" :initialTab="initialTab">
          <template slot="tab-head-james">Formation théorique</template>
          <template slot="tab-panel-james">
            <p
              class="description"
            >Nous proposons des formations théoriques autour de la notion de décrochage scolaire, de manière directe ou indirecte. Cette dernière peut faire intervenir des savoirs autour du développement de l’enfant mais aussi des aspects théoriques sur l’impact du comportement des adultes sur la psychologie de l’enfant.</p>
          </template>
          <template slot="tab-head-lily">Ateliers de supervision</template>
          <template slot="tab-panel-lily">
            <p
              class="description"
            >Nous proposons aux professionnels de l’éducation des ateliers de supervision afin de favoriser leur bien être, et indirectement, le bien être des enfants qu’ils prennent en charge.</p>
          </template>
          <template slot="tab-head-snape">Outils d'évaluation</template>
          <template slot="tab-panel-snape">
            <p
              class="description"
            >Afin de faire évoluer les actions de l’association, nous pouvons proposer pour chacune d’entre elles des questionnaires de satisfaction. Par ailleurs, nous souhaitons créer notre propre outil de dépistage permettant d’identifier le plus tôt possible les potentiels élèves décrocheurs.</p>
          </template>
          <!-- <template slot="tab-head-jul">Collaboration internationale</template>
          <template slot="tab-panel-jul">
            <p
              class="description"
            >Elle s’effectue à la fois dans la mise en place et la construction de l’outil de dépistage mais aussi dans la publication d’articles traitant ou abordant la question du décrochage scolaire.</p>
          </template>-->
        </app-tab>
        <img src="/img/actions/school.svg" alt />
      </section>
      <app-footer />
    </main>
  </div>
</template>

<script>
import AppNav from "~/components/AppNav";
import AppArticle from "~/components/AppArticle";
import AppNumber from "~/components/AppNumber";
import AppAccordion from "~/components/AppAccordion";
import AppTab from "~/components/AppTab";
import AppFooter from "~/components/AppFooter";
import AppMobile from "~/components/AppMobile";

export default {
  components: {
    AppNav,
    AppArticle,
    AppNumber,
    AppAccordion,
    AppTab,
    AppFooter,
    AppMobile,
  },
  data() {
    return {
      initialTab: "james",
      tabs: ["james", "lily", "snape"],
      where: [
        {
          question: "En milieu scolaire",
          answer:
            "Nous proposons aux établissements des permanences psychologiques spécifiques au décrochage scolaire afin d’accompagner les jeunes élèves en difficulté et d’être disponible pour l’ensemble des professionnels de l’établissement, concerné par des élèves en décrochage scolaire. Nous proposons aussi en partenariat avec les universités des tests de dépistage de potentiel décrochage.",
          open: false,
        },
        {
          question: "En extra scolaire",
          answer:
            "La prise en charge externe est principalement psychologique et psychothérapeutique et aborde la question du décrochage scolaire de façon bien plus large. Elle permet par ailleurs d’identifier si d’autres types de prise en charge pluridisciplinaires sont nécessaires.",
          open: false,
        },
      ],
      how: [
        {
          question: "En individuel",
          answer:
            "Dans le cadre d’un entretien en face à face, ou dans le cadre d’un bilan ou d’un dépistage.",
          open: false,
        },
        {
          question: "En groupe",
          answer:
            "Dans la mise en place de programmes de gestion de conflits , dans les ateliers de supervision , dans les groupes de parole ou dans les ateliers thérapeutique de remédiation.",
          open: false,
        },
        {
          question: "En institutionnel",
          answer:
            "Dans le diagnostic de fonctionnement de l’établissement et dans l’identification des sources internes génératrices de décrochage scolaire.",
          open: false,
        },
      ],
    };
  },
  methods: {
    toggleOpen: function (index) {
      this.where = this.where.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open;
        } else {
          faq.open = false;
        }

        return faq;
      });
      this.how = this.how.map((faq, i) => {
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
main section {
  padding: 0 1rem;
}
.title {
  margin-top: 10px;
  margin-bottom: 20px;
}

.description {
  margin-top: 1rem;
  margin-bottom: 1rem;
  text-align: center;
}
main section img {
  max-height: 15rem;
}

.image {
  height: 16rem;
  width: auto;
}
@media screen and (min-width: 45rem) {
  h2::before,
  h2::after {
    border-bottom: 1rem solid var(--green);
  }
  main section {
    padding: 0 5rem;
  }
}
</style>


