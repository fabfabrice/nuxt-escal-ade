<template>
  <article>
    <figure class="actu">
      <img src="/img/actu/actu-forum2019.jpg" alt="actu" />
      <figcaption>
        <h3>Forum des associations</h3>
        <h4>samedi 7 septembre 2019</h4>
        <p>ESCAL'AdE sera présente au forum des associations 2019 au gymnase Broustal à Trappes, 6 avenue Ludwig Van Beethoven</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <img src="/img/actu/actu-revisions-brevet.gif" alt="actu" />
      <figcaption>
        <h3>Ateliers de révisions pour le brevet</h3>
        <h4>du 11 mai au 22 juin 2019</h4>
        <p>
          Ateliers de révision pour le brevet chaque samedi de 9h30 à 12h30, du 11 mai au 22 juin, à la médiathèque
          Anatole France, à Trappes
        </p>
      </figcaption>
    </figure>
    <figure class="actu">
      <img src="/img/actu/actu-cinedebat.gif" alt="actu" />
      <figcaption>
        <h3>Ciné débat autour du décrochage scolaire</h3>
        <h4>Mercredi 13 mars 2019</h4>
        <p>Dans le cadre du cycle de conférence, « prévenir autrement le décrochage scolaire : quand nous faisons indoor », l’association ESCAL’AdE organise en partenariat avec le cinéma Le Grenier à Sel et la mairie de Trappes, un Ciné Débat s’appuyant sur des films de fiction autour des problématiques scolaires et d’apprentissage, avec au programme la projection du film « Les grands esprits » (2017) réalisé par Olivier Ayache, suivi d’un débat organisé par l’association ESCAL’AdE avec comme intervenant Thibault Labaille, psychologue de formation et chargé de production dans l’audiovisuel et le cinéma, ainsi que d’un buffet.</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <img src="/img/actu/actu-forum.jpg" alt="actu" />
      <figcaption>
        <h3>Forum des associations</h3>
        <h4>Samedi 9 Septembre 2018</h4>
        <p>ESCAL'AdE sera présente au forum des associations 2018 au gymnase Broustal à Trappes, 6 avenue Ludwig Van Beethoven</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <iframe
        scrolling="no"
        id="hearthis_at_track_1630205"
        height="250"
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
      <figcaption>
        <h3>Portrait de Nassira Mohamad sur Marmite FM 88.4</h3>
        <h4>Octobre 2017</h4>
        <p>Nassira Mohammad, co-fondatrice de l’association, présente sur marmite FM, décrit quelques éléments essentiels des actions de l’association lors du forum de rentrée 2017.</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <img src="/img/actu/actu-forum.jpg" alt="actu" />
      <figcaption>
        <h3>Forum des associations</h3>
        <h4>Septembre 2017</h4>
        <p>ESCAL'AdE sera présente au forum des associations 2017 au gymnase Broustal à Trappes, 6 avenue Ludwig Van Beethoven</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <img src="/img/actu/actu-ATRE.jpg" alt="actu" />
      <figcaption>
        <h3>Atelier de recherche d'entreprises</h3>
        <h4>Janvier / Avril / Septembre 2017</h4>
        <p>ESCAL'AdE organise des ateliers de recherche d'entreprises, réalisation de CV et entretien d'embauche, à destination des jeunes dès la classe de 3ème pour leur recherche de stage</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <img src="/img/actu/actu-ko-des-mots.jpg" alt="actu" />
      <figcaption>
        <h3>Ko des mots</h3>
        <h4>Avril 2017</h4>
        <p>En partenariat avec l'agence AD2, "KO DES MOTS", un atelier d'improvisation littéraire et une battle sur scène</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <iframe
        src="https://www.youtube.com/embed/yOcaTzV7pAU"
        frameborder="0"
        allowfullscreen
        class="videofull"
      ></iframe>
      <figcaption>
        <h3>Atelier de recherche d'entreprises</h3>
        <h4>Janvier / Avril / Septembre 2017</h4>
        <p>ESCAL'AdE organise des ateliers de recherche d'entreprises, réalisation de CV et entretien d'embauche, à destination des jeunes dès la classe de 3ème pour leur recherche de stage</p>
      </figcaption>
    </figure>
    <figure class="actu">
      <img src="/img/actu/actu-forum.jpg" alt="actu" />
      <figcaption>
        <h3>Forum des associations</h3>
        <h4>Septembre 2016</h4>
        <p>ESCAL'AdE sera présente au forum des associations 2016 au gymnase Broustal à Trappes, 6 avenue Ludwig Van Beethoven</p>
      </figcaption>
    </figure>
  </article>
</template>

<script>
export default {
  name: "app-article",
};
</script>

<style>
article .actu {
  padding: 1rem 0;
}
article .actu img {
  max-width: 35%;
}
.actu iframe {
  width: 100%;
  height: 100%;
}
.videofull {
  min-height: 18rem;
  max-width: 36rem;
}
@media screen and (min-width: 80rem) {
  article .actu {
    display: flex;
  }
  article .actu img {
    max-width: 23%;
  }
  .actu figcaption {
    padding-left: 3.5rem;
  }
  .actu iframe {
    width: 23%;
    min-height: 16rem;
  }
}
</style>