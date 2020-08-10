<template>
  <section class="superquote">
    <p class="textquote">
      <slot name="textquote">
        "Les espèces qui survivent ne sont pas les plus fortes,
        ni les plus intelligentes, mais celles qui s’adaptent
        le mieux aux changements."
      </slot>
      <!-- rajouter quote en :before -->
    </p>
    <p class="author">
      <slot name="author">Charles Darwin</slot>
    </p>
  </section>
</template>

<script>
export default {
  name: "app-quote",
};
</script>

<style>
.superquote {
  padding: 2rem;
  margin: 0 2rem 2rem 2rem;
  background-color: var(--yellow);
}

@media screen and (min-width: 80rem) {
  .superquote {
    padding: 3rem 5rem 1rem;
    margin: 0;
  }
}
/* <!-- rajouter quote en :before --> */
</style>