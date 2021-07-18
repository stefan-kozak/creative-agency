<template>
  <nav>
    <img class="logo" src="@/assets/cross-display/logo.svg" alt="logo" />
    <ul>
      <li><a title="About" href="#about">About</a></li>
      <li><a title="Service" href="#service">Service</a></li>
      <li><a title="Projects" href="#projects">Projects</a></li>
      <li><a href="#schedule-call">Schedule Call</a></li>
    </ul>
    <img
      id="mobile-nav-icon"
      src="@/assets/mobile/icon-hamburger.svg"
      alt="menu"
    />
  </nav>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/settings.scss";

nav {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 3em 1.5em;
  ul {
    display: none;
    li {
      margin: 1em;
      list-style: none;
      width: max-content;
      text-align: center;

      a {
        text-decoration: none;
        color: $white;

        &::before {
          display: block;
          content: attr(title);
          font-weight: 800;
          height: 0;
          overflow: hidden;
          visibility: hidden;
        }

        &:hover {
          font-weight: 800;
        }
      }

      &:last-child {
        padding: 1em 1.5em;
        background-color: $bg-black;
        a {
          color: $white;
          text-decoration: none;
          font-weight: 800;
          white-space: nowrap;
        }
        &:hover {
          background-color: lighten($bg-black, 10%);
        }
      }
    }
  }
  #mobile-nav-icon {
    width: auto;
    height: 100%;
  }
}

//RESPONSIVE

@media only screen and (min-width: 768px) {
  /* For tablets: */
  nav {
    display: flex;
    padding: 0;

    .logo {
      padding: 3em 2em;
    }

    ul {
      display: flex;
      align-items: center;
      padding: 3em 2em;
      margin: 0;
      background-color: $primary-color;
      color: $white;
    }

    #mobile-nav-icon {
      display: none;
    }
  }
}

@media only screen and (min-width: 1440px) {
  /* For desktop: */
  nav {
    width: 100%;

    .logo {
      padding: 3em 10em;
    }

    ul {
      width: 50%;
      padding-right: 0;
    }
  }
}
</style>
