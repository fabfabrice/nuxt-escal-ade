<template>
  <div id="app">
    <div class="portfolio-wrapper">
      <div class="panel-item">
        <a v-on:click="filterTag('all')">
          <span class="item">Tous</span>
        </a>
        <a v-on:click="filterTag('cat0')">
          <span class="item">Prévention</span>
        </a>
        <a v-on:click="filterTag('cat1')">
          <span class="item">Prise en charge</span>
        </a>
        <a v-on:click="filterTag('cat2')">
          <span class="item">Outils pratiques</span>
        </a>
        <a v-on:click="filterTag('cat3')">
          <span class="item">Motivations</span>
        </a>
        <a v-on:click="filterTag('cat4')">
          <span class="item">Pédagogie</span>
        </a>
      </div>
      <transition-group name="grid-container" class="grid-container" tag="section">
        <div class="content" v-for="content in filteredContents" v-bind:key="content.id">
          <a v-bind:href="content.link" target="_blank">
            <figure class="card-image">
              <img v-bind:src="content.img" v-bind:alt="content.title" />
              <figcaption>
                <h2 class="titlecard">
                  <span class="card-title">{{ content.title }}</span>
                </h2>
                <p class="card-content">{{ content.desc }}</p>
              </figcaption>
            </figure>
          </a>
        </div>
      </transition-group>
    </div>
  </div>
</template>

<script>
import lodash from "lodash";
// import image1 from "/img/8.jpg";
// import image2 from "/img/9.jpg";

export default {
  name: "app-filter",
  data() {
    return {
      search_filter: "",
      currentTag: "all",
      contents: [
        {
          id: 0,
          img: "/img/ressources/articles-diagnostic-ministere.jpg",
          title: "évaluation de la lutte contre le décrochage scolaire",
          desc:
            "Réduire le décrochage scolaire constitue un enjeu essentiel pour notre société",
          link:
            "http://www.education.gouv.fr/cid55632/la-lutte-contre-le-decrochage-scolaire.html",
          tags: ["all", "cat0", "cat1"],
        },
        {
          id: 1,
          img: "/img/ressources/articles-dispositifs.jpg",
          title: "les dispositifs du ministère de l’Education Nationale",
          desc:
            "La poursuite du plan d'action tous mobilisés pour vaincre le décrochage scolaire",
          link: "",
          tags: ["all", "cat0", "cat1"],
        },
        {
          id: 2,
          img: "/img/ressources/articles-histoire.jpg",
          title: "Les histoires dans le développement des enfants",
          desc:
            "la lecture d’histoires a une influence considérable sur la compréhension qu’ont les enfants du monde",
          link:
            "http://rire.ctreq.qc.ca/2016/02/histoires-developpement-enfants",
          tags: ["all", "cat3"],
        },
        {
          id: 3,
          img: "/img/ressources/articles-balas-decrochage.jpg",
          title: "lutter contre le décrochage scolaire Par Guillaume Balas",
          desc:
            "Le décrochage comme un phénomène évolutif dans le temps et dans l’espace",
          link:
            "https://jean-jaures.org/sites/default/files/Balas_decrochage_scolaire.pdf",
          tags: ["all", "cat0", "cat1"],
        },
        {
          id: 4,
          img: "/img/ressources/articles-accroitre-reussite.jpg",
          title: "Accroître la réussite scolaire en milieu défavorisé",
          desc:
            "Agir pour réduire les effets des inégalités sociales sur la réussite scolaire",
          link:
            "http://inshea.fr/sites/default/files/www/sites/default/files/downloads/fichiers-fiche-produits/nras56_Janosz.pdf",
          tags: ["all", "cat0"],
        },
        {
          id: 5,
          img: "/img/ressources/articles-comprendre-cerveau.jpg",
          title: "Comprendre le cerveau pour mieux apprendre à l’école",
          desc:
            "Quatre choses à retenir à propos du cerveau pour mieux apprendre à l'école",
          link:
            "http://apprendreaeduquer.fr/comprendre-le-cerveau-pour-mieux-apprendre/",
          tags: ["all", "cat3"],
        },
        {
          id: 6,
          img: "/img/ressources/articles-consequences.jpg",
          title: "Conséquences d’une vitesse de traitement réduite",
          desc:
            "La vitesse de traitement désigne la vitesse à laquelle les infos traversent le cerveau",
          link:
            "https://upbility.fr/blogs/news/consequences-d-une-vitesse-de-traitement-reduite",
          tags: ["all", "cat4"],
        },
        {
          id: 7,
          img: "/img/ressources/articles-faire-difference.jpg",
          title:
            "Les besoins d’apprentissage et la différenciation pédagogique",
          desc:
            "Philosophie et pédagogie pour la réussite des élèves dans leur diversité",
          link:
            "https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxkcmFsYWlucG91aGV0fGd4OjZjZThjNjFmNjk5ZjVkMGQ",
          tags: ["all", "cat4"],
        },
        {
          id: 8,
          img: "/img/ressources/articles-appliquer-discipline-positive.jpg",
          title: "Comment appliquer la discipline positive ?",
          desc:
            "La discipline positive comprend une approche à l’éducation et une façon de penser",
          link: "http://apprendreaeduquer.fr/appliquer-discipline-positive/",
          tags: ["all", "cat0", "cat4"],
        },
        {
          id: 9,
          img: "/img/ressources/articles-adolescent.jpg",
          title: "Interview de Sophie Chirat sur l'adolescent décrocheur",
          desc:
            "Le département du Rhône engagé dans la lutte contre le décrochage scolaire",
          link:
            "http://www.ch-le-vinatier.fr/orspere-samdarra/rhizome/anciens-numeros/rhizome-n59-les-adolescents-et-ce-qu-ils-ont-de-difficiles/ladolescent-decrocheur-une-problematique-de-leducation-nationale-1322.html",
          tags: ["all", "cat0", "cat1"],
        },
        {
          id: 10,
          img: "/img/ressources/articles-apprentissage-musique.jpg",
          title: "La musique et le développement du cerveau",
          desc:
            "La formation musicale affecte la structure et la fonction de différentes régions du cerveau",
          link:
            "http://www.psychomedia.qc.ca/musique/2013-11-14/apprentissage-effets-sur-le-developpement-cerebral",
          tags: ["all", "cat3"],
        },
        {
          id: 11,
          img: "/img/ressources/articles-eleve-anxieux.jpg",
          title: "Prévenir les comportements de l'élève anxieux",
          desc:
            "Plusieurs raisons peuvent expliquer des comportements dérangeants d'un élève anxieux",
          link:
            "http://rire.ctreq.qc.ca/2016/06/prevenir-comportements-anxieux/",
          tags: ["all", "cat0"],
        },
        {
          id: 12,
          img: "/img/ressources/articles-faiblesse-memoire.jpg",
          title: "Comment compenser des faiblesses de la mémoire de travail ?",
          desc:
            "Cinq conseils pratiques pour compenser les difficultés de la mémoire de travail",
          link:
            "http://taalecole.ca/adaptations/avis-dexperts-memoire-de-travail/",
          tags: ["all", "cat0"],
        },
        {
          id: 13,
          img: "/img/ressources/articles-aider-eleve-dys.jpg",
          title: "Comment aider l'enfant dys-orthographique ?",
          desc:
            "La dysorthographie nécessite une prise en charge adaptée selon les besoins prioritaires",
          link:
            "http://www.dys-positif.fr/comment-aider-lenfant-dysorthographique/",
          tags: ["all", "cat0"],
        },
        {
          id: 14,
          img: "/img/ressources/articles-amenagements-scolaires.jpg",
          title: "Aménagements de la scolarité chez les surdoués",
          desc:
            "Des surdoués passant le bac à 12 ans alors que d'autres sont en échec scolaire",
          link:
            "http://www.sciencesetavenir.fr/sante/20150413.OBS7053/cerveau-pourquoi-certains-surdoues-reussissent-et-d-autres-non.html",
          tags: ["all", "cat4"],
        },
        {
          id: 15,
          img: "/img/ressources/articles-aide-comprehension.jpg",
          title: "Aide à la compréhension de texte avec Liquid Text",
          desc:
            "Liquid Text est une application gratuite permettant d’être actif pendant la lecture",
          link:
            "http://wp.csmb.qc.ca/tic_ehdaa/aide-a-la-comprehension-de-texte-liquid-text/",
          tags: ["all", "cat2"],
        },
        {
          id: 16,
          img: "/img/ressources/articles-apprentissage-tdah.jpg",
          title: "Des étudiants ayant un trouble d’apprentissage",
          desc:
            "Des stratégies pour des étudiants avec des troubles d'apprentissage ou d'attention",
          link: "http://rire.ctreq.qc.ca/2016/05/strategie-ehdaa-universite/",
          tags: ["all", "cat0"],
        },
        {
          id: 17,
          img: "/img/ressources/articles-boite-problemes.jpg",
          title: "Boites à problèmes : les maths en CP-CE1",
          desc:
            "Résoudre des problèmes de maths CP-CE1 avec une méthode inspirée par la classification de Vergnaud",
          link:
            "http://grainesdelivres.eklablog.com/les-boites-a-problemes-a125890970",
          tags: ["all", "cat2"],
        },
        {
          id: 18,
          img: "/img/ressources/articles-autoregulation.jpg",
          title: "Les pratiques de l’auto-régulation à l’école",
          desc:
            "Le besoin de prendre en compte les nombreux facteurs de stress qui entourent l’apprentissage",
          link: "http://rire.ctreq.qc.ca/2016/04/autoregulation-ecole/",
          tags: ["all", "cat1", "cat4"],
        },
        {
          id: 19,
          img: "/img/ressources/articles-apprendre-dormant.jpg",
          title: "Pourquoi apprend-on mieux en dormant ?",
          desc:
            "Communication de structures cérébrales durant le sommeil pour consolider les souvenirs",
          link:
            "http://www.cerveauetpsycho.fr/ewb_pages/a/actu-pourquoi-apprend-on-mieux-en-dormant-37071.php",
          tags: ["all", "cat3"],
        },
        {
          id: 20,
          img: "/img/ressources/articles-itw-guerrieri-dys.jpg",
          title: "Interview de C.Guerrieri : aider les élèves dys",
          desc:
            "Célia Guerrieri prof de lettres dyscalculique nous parle des deux guides de survie pour dys",
          link:
            "http://www.vousnousils.fr/2016/04/11/profs-dys-eleves-solutions-586481",
          tags: ["all", "cat0"],
        },
        {
          id: 21,
          img: "/img/ressources/articles-troubles-praxiques.jpg",
          title: "Conférence de C. Huron sur les troubles praxiques",
          desc:
            "Explications des difficultés et aménagements pour les enfants avec troubles praxiques",
          link:
            "http://www.bloghoptoys.fr/troubles-praxiques-a-lecole-conference-de-caroline-huron",
          tags: ["all", "cat0"],
        },
        {
          id: 22,
          img: "/img/ressources/articles-dyspraxie.jpg",
          title: "La dyspraxie : qu’est-ce que c’est ?",
          desc:
            "Pathologiquement maladroits : ils se cognent, ils tombent, ils renversent ils cassent, ils ont du mal à manger proprement",
          link:
            "http://www.dysmoi.fr/troubles-dapprentissage/dyspraxie/dyspraxie-quest-ce-cest/",
          tags: ["all", "cat0"],
        },
        {
          id: 23,
          img: "/img/ressources/articles-discipline-positive.jpg",
          title: "La discipline positive par Joan E. Durrant",
          desc:
            "L’éducation des enfants peut se révéler une aventure joyeuse décourageante et épuisante",
          link:
            "http://www.cheo.on.ca/uploads/advocacy/JS_Positive_Discipline_French_2nd_edition.pdf",
          tags: ["all", "cat0", "cat2"],
        },
        {
          id: 24,
          img: "/img/ressources/articles-troubles-apprentissage.jpg",
          title: "Troubles de l'apprentissage: les fiches outils",
          desc:
            "Trucs et astuces sont précieux pour mémoriser les mots ou les tables de multiplication",
          link:
            "http://www.cathobel.be/2016/04/29/troubles-de-lapprentissage-pratiques-fiches-outil/",
          tags: ["all", "cat0", "cat2"],
        },
        {
          id: 25,
          img: "/img/ressources/articles-representation-mentale.jpg",
          title: "Les niveaux de représentation mentale d’un texte",
          desc:
            "les niveaux de représentation mentale d’un texte proposés par Van Dijk et Kintsch (1983)",
          link:
            "http://parlonsapprentissage.com/les-niveaux-de-representation-mentale-dun-texte/",
          tags: ["all", "cat2"],
        },
        {
          id: 26,
          img: "/img/ressources/articles-neuro-psycho.jpg",
          title: "Pédagogie neuro-psychologie psychologie orthophonie",
          desc:
            "Dossiers sur les différents profils et la prise en charge des surdoués par l’ANPEIP",
          link:
            "https://drive.google.com/file/d/0B7CTwDMIlMbKQjVtS2l3Zk1hOVk/view?pref=2&pli=1",
          tags: ["all", "cat4"],
        },
        {
          id: 27,
          img: "/img/ressources/articles-trousse-evaluation.jpg",
          title: "Trousse d’évaluation des décrocheurs scolaires",
          desc:
            "La trousse contient un questionnaire, un logiciel, et un manuel",
          link:
            "http://www.tableeducationoutaouais.com/files/4712/8741/0014/trousse_evaluation_decrocheurs_potentiels.pdf",
          tags: ["all", "cat1", "cat2"],
        },
        {
          id: 28,
          img: "/img/ressources/articles-surdoues.jpg",
          title: "Pourquoi certains surdoués réussissent et d'autres non ?",
          desc:
            "Des surdoués passent le bac à 12 ans alors que d'autres sont en échec scolaire",
          link:
            "http://www.sciencesetavenir.fr/sante/20150413.OBS7053/cerveau-pourquoi-certains-surdoues-reussissent-et-d-autres-non.html",
          tags: ["all", "cat0"],
        },
        {
          id: 29,
          img: "/img/ressources/articles-cerveau.jpg",
          title: "Variations du cerveau selon la pédagogie appliquée",
          desc:
            "La pédagogie de Manuela Piazza et Céline Alvarez à l’école Jean-Lurçat de Gennevilliers",
          link:
            "http://www.telerama.fr/monde/le-cerveau-d-un-enfant-varie-selon-la-pedagogie-qu-on-lui-applique,137987.php?utm_campaign=Echobox&utm_medium=Social&utm_source=Facebook#link_time=1455874379",
          tags: ["all", "cat4"],
        },
        {
          id: 30,
          img: "/img/ressources/articles-maths.jpg",
          title: "18 idées géniales pour faire aimer les maths à vos enfants",
          desc:
            "Des activités divertissantes pour faire aimer les maths tout en progressant",
          link:
            "http://desidees.net/18-idees-distrayantes-travailler-maths-vos-enfants/",
          tags: ["all", "cat2"],
        },
        {
          id: 31,
          img: "/img/ressources/articles-itw-roozs.jpg",
          title: "Le risque pour l'élève dys d'échouer durablement",
          desc:
            "Selon Jean Michel Roosz le système de prise en charge des dys à l'Ecole est dangereux",
          link:
            "http://www.vousnousils.fr/2016/06/01/pap-le-risque-pour-leleve-dys-est-dechouer-durablement-588765",
          tags: ["all", "cat0"],
        },
        {
          id: 32,
          img: "/img/ressources/articles-contrer-decrochage.jpg",
          title: "Contrer le décrochage scolaire à la fin du secondaire",
          desc:
            "Guide pour aider à prévenir le décrochage scolaire des élèves de 4e et 5e",
          link:
            "http://www.reussiteeducativeestrie.ca/dynamiques/biblio_ens_prof/contrer_decrochage_fr.pdf",
          tags: ["all", "cat1", "cat2"],
        },
        {
          id: 33,
          img: "/img/ressources/articles-methodes.jpg",
          title: "10 méthodes pour réviser et apprendre efficacement",
          desc:
            "Comment dire au cerveau que l’information consultée et apprise est importante ?",
          link:
            "http://apprendreaeduquer.fr/quelques-methodes-reviser-memoriser-apprendre-efficacement/",
          tags: ["all", "cat4"],
        },
        {
          id: 34,
          img: "/img/ressources/articles-memorisation.jpg",
          title: "Mémorisation et oubli : retenir une leçon",
          desc:
            "Comment retenir efficacement une leçon ? Comment faire pour ne pas oublier ses leçons ?",
          link: "http://www.dysmoi.fr/memorisation-et-oubli-retenir-une-lecon/",
          tags: ["all", "cat2"],
        },
        {
          id: 35,
          img: "/img/ressources/articles-janosz-assise-regionale.jpg",
          title: "Décrochage scolaire : Québec mise sur la prévention",
          desc:
            "Itw de M. Janosz aux assises régionales de lutte contre le décrochage scolaire",
          link:
            "http://www.iledefrance.fr/fil-actus-region/decrochage-scolaire-quebec-mise-prevention",
          tags: ["all", "cat0"],
        },
        {
          id: 36,
          img: "/img/ressources/articles-habilites-graphomotrices.jpg",
          title: "Les habiletés graphomotrices une composante sous-estimée",
          desc:
            "écrire c’est aussi développer des compétences relevant des habiletés motrices de l’enfant",
          link: "http://rire.ctreq.qc.ca/2016/03/habiletes-graphomotrices/",
          tags: ["all", "cat3", "cat4"],
        },
        {
          id: 37,
          img: "/img/ressources/articles-troubles-apprentissage.jpg",
          title: "Difficultés ou troubles d'apprentissage ?",
          desc:
            "Zoé est incapable de différencier les signes les plus grands et les plus petits",
          link:
            "http://www.mamanpourlavie.com/vie-scolaire/apprentissages/11877-difficulte-ou-trouble-d-apprentissage.thtml",
          tags: ["all", "cat0"],
        },
        {
          id: 38,
          img: "/img/ressources/articles-images-pour-parler.jpg",
          title: "Des images pour parler, donner envie d’apprendre",
          desc:
            "Des images pour apprendre à décrire et faire des conjectures ainsi que s'exprimer",
          link:
            "http://lavieenclasse.eklablog.com/images-pour-parler-a112656604",
          tags: ["all", "cat2"],
        },
        {
          id: 39,
          img: "/img/ressources/articles-glassman.jpg",
          title: "Le décrochage scolaire par Dominique Glassmann",
          desc:
            "Le décrochage scolaire est un objet aux contours flous réunissant divers enjeux, dépassant les institutions.",
          link:
            "http://www.crefe38.fr/IMG/pdf/GLASMAN_VEI2000_decrochagescolaire.pdf",
          tags: ["all", "cat1"],
        },
        {
          id: 40,
          img: "/img/ressources/articles-guide-dys.jpg",
          title: "Guide pratique les dys en classe",
          desc:
            "Les troubles dys concernent les fonctions cognitives. Ces fonctions représentent tous les processus cérébraux",
          link:
            "http://blog.ac-rouen.fr/clg-montesquieu-dispositif-ulis-tsl/files/2016/02/GUIDE-LES-DYS-EN-CLASSE.pdf",
          tags: ["all", "cat2", "cat4"],
        },
      ],
    };
  },
  computed: {
    filteredContents: function () {
      let tempTag = this.currentTag;
      return this.contents
        .filter(function (item) {
          return item.tags.indexOf(tempTag) !== -1;
        })
        .filter((item) => {
          return item.title.match(this.search_filter);
        });
    },
  },
  methods: {
    filterTag: function (tag) {
      this.currentTag = tag;
    },
    shuffleTag: function () {
      this.contents = _.shuffle(this.contents);
    },
  },
};
</script>

<style>
html,
body {
  background-color: #f9f9f9;
  height: 100%;
  width: 100%;
}
[v-cloak] {
  display: none;
}
.panel-item {
  position: relative;
  text-align: center;
  margin: 10px 0px 10px 0px;
}
.panel-item > a {
  display: inline-flex;
  padding: 18px 20px;
  text-decoration: none;
  font-size: 20px;
}
.panel-item > a:hover {
  color: var(--font);
}
.item {
  position: relative;
  cursor: pointer;
}
.item::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  transform: scaleX(0);
  transform-origin: bottom;
  transition: transform 0.25s ease-out;
}
.item:hover::after {
  background-color: var(--font);
  transform: scaleX(1);
  transform-origin: bottom center;
}
.grid-container {
  display: grid;
  grid-gap: 2em;
  grid-template-columns: repeat(auto-fit, minmax(auto, 320px));
  grid-auto-rows: 1fr;
  justify-content: center;
  grid-auto-flow: dense;
}
.grid-container-enter-active,
.grid-container-leave-active {
  transition: all 1s ease;
}
.grid-container-enter,
.grid-container-leave-to {
  opacity: 0;
}
.content {
  width: 320px;
  transition: all 0.8s ease;
}
.content > a {
  text-decoration: none;
  color: #888;
  cursor: pointer;
}

/* Common style */
.card-image {
  position: relative;
  float: left;
  overflow: hidden;
  margin: 0;
  min-width: 320px;
  max-width: 480px;
  max-height: 360px;
  width: 48%;
  height: auto;
  background: #3085a3;
  text-align: center;
  cursor: pointer;
  font-family: "Nunito", sans-serif;
}

.card-image img {
  position: relative;
  display: block;
  /* min-height: 100%;
  max-width: 100%; */
  opacity: 0.7;
}

.card-image figcaption {
  color: #fff;
  text-transform: uppercase;
  font-size: 1.25em;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.card-image figcaption::before,
.card-imagefigcaption::after {
  pointer-events: none;
}

.card-image figcaption,
.card-image figcaption > a {
  position: absolute;
  top: 0;
  left: 0;
}

/* Anchor will cover the whole item by default */
/* For some effects it will show as a button */
.card-image figcaption > a {
  z-index: 1000;
  text-indent: 200%;
  white-space: nowrap;
  font-size: 0;
  opacity: 0;
}

.card-image h2 {
  font-weight: 300;
  line-height: 1;
}

.card-image h2 span {
  font-weight: 900;
  font-size: 1.3rem;
  line-height: 1.15;
}

.card-image h2,
.card-image p {
  margin: 0;
}

.card-image p {
  letter-spacing: 1px;
  font-size: 68.5%;
}

/* Individual effects */

.card-image {
  background: #030c17;
}

.card-image img {
  opacity: 0.7;
  -webkit-transition: opacity 0.35s;
  transition: opacity 0.35s;
}

.card-image figcaption::before {
  position: absolute;
  top: 30px;
  right: 30px;
  bottom: 30px;
  left: 30px;
  border: 2px solid #fff;
  box-shadow: 0 0 0 30px rgba(255, 255, 255, 0.2);
  content: "";
  opacity: 0;
  -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  transition: opacity 0.35s, transform 0.35s;
  -webkit-transform: scale3d(1.4, 1.4, 1);
  transform: scale3d(1.4, 1.4, 1);
}

.card-image h2 {
  margin: 15% 10% 0;
  -webkit-transition: -webkit-transform 0.35s;
  transition: transform 0.35s;
  letter-spacing: 2px;
}

.card-image p {
  padding: 0.5rem 2rem 2rem 2rem;
  line-height: 1.5;
  opacity: 0;
  -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  transition: opacity 0.35s, transform 0.35s;
  -webkit-transform: scale(1.5);
  transform: scale(1.5);
  margin: 2rem 1rem;
  font-size: 0.75rem;
  font-weight: 500;
}

.card-image:hover h2 {
  -webkit-transform: scale(0.9);
  transform: scale(0.9);
}

.card-image:hover figcaption::before,
.card-image:hover p {
  opacity: 1;
  -webkit-transform: scale3d(1, 1, 1);
  transform: scale3d(1, 1, 1);
}

.card-image:hover figcaption {
  background-color: rgba(58, 52, 42, 0);
}

.card-image:hover img {
  opacity: 0.35;
}

/* Media queries */
@media screen and (max-width: 50em) {
  .card-image {
    display: inline-block;
    float: none;
    margin: 3% auto;
    width: 100%;
  }
}
</style>