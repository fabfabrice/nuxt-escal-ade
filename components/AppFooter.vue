<template>
  <footer>
    <a href="https://www.facebook.com/escal.ade.desco">
      <img src="../static/img/facebook.svg" alt="facebook" color="blue" />
    </a>
    <a href="https://www.facebook.com/escal.ade.desco">
      <img src="../static/img/twitter.svg" alt="twitter" />
    </a>
    <a href="mailto:association.escal.ade@gmail.com">
      <img src="../static/img/envelop.svg" alt="envelop" />
    </a>
    <nuxt-link to="/mentions-legales">
      <p>Mentions légales</p>
    </nuxt-link>
  </footer>
</template>

<script>
export default {
  name: "app-footer",
};
</script>

<style>
footer {
  text-align: center;
  margin: 3rem 0;
}
footer div {
  display: flex;
  justify-content: center;
  padding: 1.5rem 0 0.5rem;
}
footer a img {
  max-width: 3rem;
  margin: 0 0.4rem;
  border-radius: 10px;
  background: var(--font);
  padding: 0.5rem;
}
</style>
