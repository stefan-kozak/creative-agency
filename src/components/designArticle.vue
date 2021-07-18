<template>
  <section>
    <article>
      <img
        class="mobile-image"
        src="@/assets/mobile/image-strategic.jpg"
        alt="strategic"
      />
      <img
        class="tablet-image"
        src="@/assets/tablet/image-strategic.jpg"
        alt="strategic"
      />
      <img
        class="desktop-image"
        src="@/assets/desktop/image-strategic.jpg"
        alt="strategic"
      />
      <img
        class="svg"
        src="@/assets/cross-display/bg-pattern-wave-red.svg"
        alt="svg"
      />
    </article>

    <div>
      <h2><strong>Design</strong> is strategic.</h2>
      <p>
        “A well-crafted design strategy consistently produces desired outcomes
        and brand awareness. We are firm believers that success lies in creative
        collaboration with our clients.”
      </p>
      <a href="#schedule-a-call">Schedule a Call</a>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/settings.scss";

section {
  margin-top: 20%;
  background-color: $bg-black;
  position: relative;

  article {
    position: relative;

    img.mobile-image {
      display: block;
      width: 100%;
    }

    img.tablet-image {
      display: none;
    }

    img.desktop-image {
      display: none;
    }

    .svg {
      position: absolute;
      left: 1.5em;
      bottom: -0.5em;
      width: 20%;
      z-index: 10;
    }

    .svg {
      bottom: -8%;
      left: 7%;
    }
  }

  div {
    padding: 1.5em;
    display: flex;
    flex-direction: column;
    color: $white;

    h2 {
      font-size: em(32);
      white-space: nowrap;
      margin: 0.3em 0;

      strong {
        color: $primary-color;
      }
    }

    p {
      font-size: em(15);
      line-height: em(32);
    }

    a {
      text-decoration: none;
      border-bottom: 1px solid $primary-color;
      padding-bottom: 0.5em;
      width: max-content;
      color: $primary-color;
      margin-top: 2em;
      font-weight: 800;

      &:hover {
        color: lighten($primary-color, 5%);
        border-color: lighten($primary-color, 5%);
      }
    }
  }
}

//RESPONSIVE

@media only screen and (min-width: 768px) {
  /* For tablets: */
  section {
    margin-top: 0;
    display: flex;
    flex-direction: row;

    article {
      width: 50%;

      img.mobile-image {
        display: none;
      }

      img.tablet-image {
        display: block;
        width: 100%;
      }

      img.desktop-image {
        display: none;
      }

      .svg {
        width: 15%;
        bottom: 77%;
        left: 92%;
      }
    }

    div {
      width: 35%;
      margin-top: 5%;
      padding: 3em 4em;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;

      h2 {
        font-size: em(32);
        width: 50%;
        white-space: normal;
        line-height: 40px;
      }
    }
  }
}

@media only screen and (min-width: 1440px) {
  /* For desktop: */
  section {
    article {
      img.mobile-image {
        display: none;
      }

      img.tablet-image {
        display: none;
      }

      img.desktop-image {
        display: block;
        width: 100%;
      }
    }

    div {
      padding: 3em 6em;

      h2 {
        font-size: em(56);
        line-height: 4rem;
      }

      p {
        font-size: em(18);
        line-height: 2rem;
      }

      a {
        font-size: em(18);
      }
    }
  }
}
</style>
