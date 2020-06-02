<template>
  <section class="superquote">
    <p class="textquote">
      <slot
        name="textquote"
      >Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias, animi. Odit earum voluptate cumque rem, laudantium obcaecati modi tempore laborum, architecto quasi cupiditate inventore recusandae sint molestiae omnis, accusamus ex. Natus maxime voluptate aliquam beatae, repellat aliquid possimus, nesciunt molestias ex obcaecati delectus officia porro, harum dolor. Voluptates voluptas saepe neque atque! Excepturi at deleniti mollitia reiciendis quia rerum sapiente similique laboriosam quas exercitationem architecto, earum quo quis ullam nisi fugiat totam, nihil debitis blanditiis labore in eligendi accusantium! Quos blanditiis consequatur porro, asperiores maxime quasi vitae eveniet et voluptatum quaerat fugit saepe, similique, quidem deserunt eius reiciendis natus dolore!</slot>
      <!-- rajouter quote en :before -->
    </p>
    <p class="author">
      <slot name="author">Justine</slot>
    </p>
  </section>
</template>

<script>
export default {
  name: "app-quote"
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