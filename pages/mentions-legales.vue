<template>
  <div>
    <app-mobile />
    <app-nav />
    <main>
      <p style="font-weight:bold;text-transform:uppercase">Mentions légales</p>
      <p>
        Ce site est la propriété de l'association ESCAL'AdE, inscrite au
        Registre du Commerce et des Sociétés de Bobigny sous le numéro RCS B 429
        617 244
      </p>
      <p>
        53 rue Hector Berlioz
        <br />78000 Trappes
        <br />06 76 35 28 67
      </p>
      <p>
        Conception du site et direction de la publication : Florian Viéville
        <br />(ancienne version du site par Célina Oliveira)
      </p>
      <p>
        Création du logo : Edith Arsen-Zahed
        <br />Vectorisation du logo: François Godard Pfister
      </p>
      <p>Hébergeur : OVH</p>
      <p>
        Données personnelles : Conformément à la Loi n°78-17 du 6 Janvier 1978,
        relative à l’informatique, aux fichiers et aux libertés, dite loi
        Informatique et Libertés, vous disposez des droits d’opposition, d’accès
        et de rectification des données vous concernant auprès de l'entreprise
        ESCAL'AdE.
      </p>
    </main>
  </div>
</template>

<script>
export default {
  components: {
    AppNav,
    AppMobile,
  },
};
import AppNav from "~/components/AppNav";
import AppFooter from "~/components/AppFooter";
import AppMobile from "~/components/AppMobile";
</script>

<style scoped>
div {
  background-color: #fff;
}
main {
  margin: 0 1rem;
  padding: 8rem 0;
  background-color: #fff;
}
main section {
  padding: 0 1rem;
}
</style>
