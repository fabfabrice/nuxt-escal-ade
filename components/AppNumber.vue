<template>
  <article class="numbercontainer">
    <div class="number">
      <slot name="number">1</slot>
    </div>
    <p class="textnumber">
      <slot
        name="textnumber"
      >Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta veniam recusandae eaque, quisquam neque exercitationem.</slot>
    </p>
  </article>
</template>

<script>
export default {
  name: "app-number"
};
</script>

<style>
.numbercontainer {
  margin-bottom: 1rem;
}
article .number {
  border-radius: 70%;
  background-color: var(--green);
  display: inline-block;
  width: 3rem;
  height: 3rem;
  padding: 0.8rem 1.2rem;
  margin-bottom: 1rem;
}
article .textnumber {
  overflow: hidden;
}
@media screen and (min-width: 80rem) {
  article .number {
    float: left;
  }
  article .textnumber {
    padding: 0.1rem 0 0 1rem;
    margin: 0;
  }
}
</style>