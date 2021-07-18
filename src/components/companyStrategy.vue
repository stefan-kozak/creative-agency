<template>
  <section>
    <h1>Our approach for creating a winning brand</h1>
    <div>
      <article>
        <h1>01</h1>
        <h3>Brand Strategy</h3>
        <p>
          Brand strategy is critical for long-term success. Outshining
          competitors and capturing the target audience are key.
        </p>
      </article>
      <article>
        <h1>02</h1>
        <h3>Brand Design</h3>
        <p>
          Keeping the brand design unique and meaningful helps in communicating
          the brand’s value effectively.
        </p>
      </article>
      <article>
        <h1>03</h1>
        <h3>Web Design</h3>
        <p>
          A beautifully crafted website is the best tool for brand awareness,
          and ultimately results in increased revenues.
        </p>
      </article>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/settings.scss";

section {
  padding: 1.5em;
  color: $white;
  background-color: $primary-color;

  h1 {
    font-size: em(32);
    font-weight: 800;
  }

  div {
    margin-top: 30%;

    article {
      position: relative;
      margin-bottom: 5em;

      h1 {
        font-weight: 800;
        opacity: 0.25;
        position: absolute;
        margin: 0;
        left: -5%;
        top: -45%;
        font-size: em(80);
        z-index: 20;
      }

      h3 {
        font-weight: 800;
        font-size: em(15);
      }
    }
    p {
      font-size: em(15);
      line-height: em(25);
      margin-top: 2em;
    }
  }
}

//RESPONSIVE

@media only screen and (min-width: 768px) {
  /* For tablets: */
  section {
    background-color: $white;
    display: flex;
    flex-direction: row;
    padding: 0;
    width: 100%;
    position: relative;
    justify-content: space-between;

    h1 {
      font-size: 2rem;
      color: $text-black;
      font-weight: 800;
      width: 37%;
      padding: 2rem;
      margin-top: 10%;
    }

    div {
      width: 45%;
      position: relative;
      right: 0;
      top: 0;
      background-color: $primary-color;
      padding: 3em 3em;
      padding-top: 7.5em;
      margin-top: -5em;
      z-index: 10;

      article {
        position: relative;
        margin-bottom: 5em;
        margin-left: 2em;

        h1 {
          color: $white;
          left: -15%;
          top: -72%;
          opacity: 0.25;
        }

        h3 {
          font-weight: 800;
          font-size: em(15);
        }
      }
      p {
        font-size: em(15);
        line-height: em(25);
        margin-top: 2em;
      }
    }
  }
}

@media only screen and (min-width: 1440px) {
  /* For desktop: */
  section {
    justify-content: space-between;
    position: relative;

    h1 {
      font-size: em(56);
      padding: 10rem;
      margin-top: 0;
      line-height: 4rem;
      position: absolute;
      z-index: 100;
    }

    div {
      width: 50%;
      padding: 10em;
      margin-top: -10em;
      margin-left: auto;

      article {
        margin-bottom: 10em;
        margin-left: 10em;

        h1 {
          left: -25%;
          top: -165%;
          opacity: 0.25;
        }

        h3 {
          font-size: em(20);
        }
        p {
          font-size: em(18);
        }
      }
    }
  }
}
</style>
