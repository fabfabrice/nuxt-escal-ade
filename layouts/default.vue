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
  --red-hover: #e57f62;
  --blue: #ceedef;
  --blue-hover: #c1dddd;
  --yellow: #fff59b;
  --yellow-hover: #ede18b;
  --green: #cfe09b;
  --green-hover: #c1ce90;
  --grey: #b0bbd1;
  --orange: #feb131;
  --orange-hover: #efa328;
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
  padding: 15rem 1rem 0rem;
  font-weight: 800;
}
h1 span {
  font-size: 2rem;
  line-height: 1.8;
  display: block;
  color: var(--white);
}
h1 {
  padding: 0;
  color: var(--font);
  font-weight: 800;
  text-align: center;
  padding: 6.5rem 0 2rem;
  margin-bottom: 1.5rem;
  /* font-size: 2.6rem; */
}
h2 {
  font-size: 1.6rem;
  font-weight: 800;
  display: flex;
  text-transform: uppercase;
  align-items: center;
  text-align: center;
  margin: 4rem 0 2rem 0;
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
  margin-bottom: 1.6rem;
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
.btn-bg {
  margin: 0.5rem 0 1rem;
}
.btn-bg,
.btn-border {
  text-transform: uppercase;
  border-radius: 0.5rem;
  font-weight: 800;
  text-align: center;
  color: var(--font);
  padding: 1rem;
}
.btn-border {
  border: 1px solid var(--red);
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
}
</style>
