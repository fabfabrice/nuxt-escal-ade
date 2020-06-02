<template>
  <nuxt />
</template>

<script>
export default {};
</script>

<style>
:root {
  --font: #2a6c8a;
  --display: #719eb2;
  --hover: rgba(0, 0, 0, 0.1);
  --white: #f5f5f5;
  --red: #ff8c6b;
  --blue: #ceedef;
  --yellow: #fff59b;
  --green: #cfe09b;
  --grey: #b0bbd1;
  --orange: #feb131;
  --beige: #f7e4d1;
  --transition: all 0.3s linear;
  --spacing: 2px;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Nunito", sans-serif;
  color: var(--font);
  line-height: 1.4;
  font-size: 1rem;
}
h1,
h2,
h3,
h4 {
  text-transform: uppercase;
  letter-spacing: 3px;
}
.slogan {
  padding: 14rem 1rem 2rem;
  font-weight: 800;
}
h1 span {
  font-size: 2.3rem;
  line-height: 1.8;
  display: block;
  color: var(--white);
}
h1 {
  padding: 0;
  color: var(--font);
  font-weight: 800;
  text-align: center;
  padding: 6rem 0 3rem;
  /* font-size: 2.6rem; */
}
h2 {
  font-size: 1.6rem;
  font-weight: 800;
  display: flex;
  text-transform: uppercase;
  align-items: center;
  text-align: center;
  margin: calc(2rem + 3vw) auto;
  display: flex;
}
h2::before {
  margin-right: 1.5rem;
}
h2::after {
  margin-left: 1.5rem;
}
h2::before,
h2::after {
  content: "";
  flex: 1;
  border-bottom: none;
}
h3 {
  font-size: 1.4rem;
  font-weight: 200;
  margin: 1rem 0 0;
}
h4 {
  color: var(--red);
  font-style: italic;
  margin-bottom: 1rem;
}
p {
  font-size: 1rem;
  margin-bottom: 1.25rem;
}
a {
  text-decoration: none;
  letter-spacing: var(--spacing);
  color: var(--font);
}
a:hover {
  color: var(--font);
}
a span {
  display: block;
}
figcaption a span {
  color: var(--red);
  text-decoration: underline;
}
img {
  max-width: 100%;
}
.btn-bg,
.btn-border {
  text-transform: uppercase;
  border-radius: 0.5rem;
  font-weight: 800;
  text-align: center;
  display: block;
  color: var(--font);
  padding: 1.2rem;
}
.btn-border {
  border: 1px solid var(--red);
}
.btn-bg {
  background-color: var(--red);
}
.btn-border:hover,
.btn-bg:hover {
  transition: var(--transition);
}
.btn-bg:hover {
  background-color: #e07d62;
}
.btn-border:hover {
  background-color: #ffe3db;
}
@media screen and (min-width: 28rem) {
  /* 450px */
  .btn-bg,
  .btn-border {
    display: inline-block;
  }
  .btn-bg {
    margin: 1rem 0;
  }
}
</style>
