<template>
  <section>
    <img
      class="svg"
      src="@/assets/cross-display/bg-pattern-wave-red.svg"
      alt="svg"
    />

    <h1>Let's build something great together.</h1>

    <a href="#schedule-call">Schedule a Call</a>
  </section>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/settings.scss";

section {
  background-color: $white;
  display: flex;
  flex-direction: column;
  padding: 1.5em;
  padding-bottom: 5em;

  h1 {
    font-size: em(32);
    font-weight: 800;
    margin-bottom: 1.5em;
  }

  a {
    font-size: em(16);
    background-color: $primary-color;
    padding: 1.5em 2em;
    font-weight: 800;
    color: $white;
    width: max-content;
    height: max-content;
    text-decoration: none;

    &:hover {
      background-color: lighten($primary-color, 5%);
    }
  }
  .svg {
    display: none;
  }
}

//RESPONSIVE

@media only screen and (min-width: 768px) {
  /* For tablets: */
  section {
    flex-direction: row;
    padding: 2em;
    align-items: center;
    padding-bottom: 5em;

    h1 {
      margin: 1em;
    }

    a {
      white-space: nowrap;
    }
  }
}

@media only screen and (min-width: 1440px) {
  /* For desktop: */
  section {
    justify-content: flex-end;
    padding: 3em 10em;
    position: relative;

    h1 {
      font-size: em(56);
      width: 69%;
      line-height: 4rem;
    }
    a {
      font-size: em(16);
    }
    .svg {
      display: block;
      position: absolute;
      left: -5%;
    }
  }
}
</style>
