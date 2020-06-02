<template>
  <article>
    <figure class="actu">
      <img src="/img/actu/actu2.png" alt="actu" />
      <figcaption>
        <h3>Forum des associations</h3>
        <h4>samedi 9 septembre 2019</h4>
        <p>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit.
          Itaque autem voluptatibus iure accusamus assumenda ullam.
        </p>
      </figcaption>
    </figure>
  </article>
</template>

<script>
export default {
  name: "app-article"
};
</script>

<style>
article .actu {
  padding: 1rem 0;
}
@media screen and (min-width: 80rem) {
  article .actu {
    display: flex;
  }
  .actu figcaption {
    padding-left: 3.5rem;
  }
}
</style>