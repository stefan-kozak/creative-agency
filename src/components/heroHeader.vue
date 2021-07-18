<template>
  <header>
    <img
      class="mobile-image"
      src="@/assets/mobile/image-hero.jpg"
      alt="header img"
    />
    <img
      class="tablet-image"
      src="@/assets/tablet/image-hero.jpg"
      alt="header img"
    />
    <img
      class="desktop-image"
      src="@/assets/desktop/image-hero.jpg"
      alt="header img"
    />
    <section>
      <h1>Branding & website design agency</h1>
      <p>
        We specialize in visual storytelling by creating cohesive brand and
        website design solutions for small businesses, giving lasting
        impressions to audiences in a digital world.
      </p>
      <a href="#learn-more">Learn More</a>
    </section>
  </header>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/settings.scss";

header {
  img.mobile-image {
    width: 100%;
  }

  img.tablet-image {
    display: none;
  }

  img.desktop-image {
    display: none;
  }

  section {
    padding: 1.5em;
    display: flex;
    flex-direction: column;

    h1 {
      font-size: em(40);
      font-weight: 800;
      margin: 0.3em 0em;
    }

    p {
      font-size: em(15);
      line-height: em(25);
    }

    a {
      background-color: $primary-color;
      color: $white;
      text-decoration: none;
      padding: 1.5em 2em;
      font-size: em(18);
      font-weight: 800;
      width: max-content;
      margin-top: 1em;

      &:hover {
        background-color: lighten($primary-color, 5%);
      }
    }
  }
}

//RESPONSIVE

@media only screen and (min-width: 768px) {
  // NEED REWORK AS FLEXBOX
  /* For tablets: */
  header {
    position: relative;

    img.mobile-image {
      display: none;
    }

    img.tablet-image {
      display: block;
      margin-left: auto;
    }

    img.desktop-image {
      display: none;
    }

    section {
      width: 50%;
      position: absolute;
      left: 0;
      top: 10%;
      padding: 2em;

      h1 {
        font-size: em(56);
      }
    }
  }
}

@media only screen and (min-width: 1440px) {
  /* For desktop: */
  header {
    position: relative;

    img.mobile-image {
      display: none;
    }

    img.tablet-image {
      display: none;
    }

    img.desktop-image {
      display: block;
      margin-left: auto;
    }

    section {
      width: 34%;
      position: absolute;
      left: 0;
      top: 10%;
      padding: 0 10em;

      h1 {
        font-size: em(80);
      }

      p {
        font-size: em(18);
        line-height: 2rem;
      }
    }
  }
}
</style>
