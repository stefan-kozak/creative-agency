<template>
  <nav>
    <img class="logo" src="@/assets/cross-display/logo.svg" alt="logo" />
    <ul id="nav-items">
      <li><a title="About" href="#about">About</a></li>
      <li><a title="Service" href="#service">Service</a></li>
      <li><a title="Projects" href="#projects">Projects</a></li>
      <li><a href="#schedule-call">Schedule Call</a></li>
    </ul>
    <div id="menu-btn" @click="menuToggle">
      <div class="menu-icon"></div>
    </div>
  </nav>
</template>

<script>
export default {
  methods: {
    menuToggle() {
      const menuBtn = document.getElementById("menu-btn");
      const subNav = document.getElementById("nav-items");
      let menuOpen = menuBtn.classList.contains("open");

      if (!menuOpen) {
        menuBtn.classList.add("open");
        subNav.classList.add("nav-open");
      } else {
        menuBtn.classList.remove("open");
        subNav.classList.remove("nav-open");
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/settings.scss";

nav {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 3em 1.5em;
  position: relative;

  #nav-items {
    margin: 0;
    top: 100%;
    right: 5%;
    padding: 1em;
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background-color: $bg-black;
    opacity: 0;

    &.nav-open {
      opacity: 1;
    }

    li {
      margin: 1em;
      list-style: none;
      width: max-content;
      align-self: center;
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
        padding: 1.5em 3em;
        background-color: $primary-color;
        a {
          color: $white;
          text-decoration: none;
          font-weight: 800;
          white-space: nowrap;
        }
        &:hover {
          background-color: lighten($primary-color, 10%);
        }
      }
    }
  }
  #menu-btn {
    width: auto;
    height: auto;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: background-color 0.2s, transform 0.5s ease;

    .menu-icon {
      width: 2em;
      height: 5px;
      background-color: $bg-black;
      border-radius: 3px;
      transition: background-color 0.2s, transform 0.5s ease;
    }

    .menu-icon::before,
    .menu-icon::after {
      content: "";
      width: 2em;
      height: 5px;
      background-color: $bg-black;
      position: absolute;
      border-radius: 3px;
      transition: background-color 0.2s, transform 0.5s ease;
    }

    .menu-icon::before {
      transform: translateY(-0.7em);
    }
    .menu-icon::after {
      transform: translateY(0.7em);
    }

    &.open .menu-icon {
      background-color: transparent;
    }

    &.open .menu-icon::before {
      transform: rotate(45deg);
    }

    &.open .menu-icon::after {
      transform: rotate(-45deg);
    }
  }
}

//RESPONSIVE

@media only screen and (min-width: 768px) {
  /* For tablets: */
  nav {
    display: flex;
    padding: 0;
    overflow: hidden;

    .logo {
      padding: 3em 2em;
    }

    #nav-items {
      display: flex;
      align-items: center;
      padding: 3em 2em;
      margin: 0;
      background-color: $primary-color;
      color: $white;
      position: relative;
      flex-direction: row;
      right: 0;
      top: 0;
      justify-content: flex-start;
      opacity: 1;

      li {
        margin: 1em 1.5em;
      }

      li:last-child {
        padding: 1em 1.5em;
        background-color: $bg-black;

        &:hover {
          background-color: lighten($bg-black, 10%);
        }
      }
    }

    #menu-btn {
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

    #nav-items {
      width: 50%;
      padding-right: 0;
    }
  }
}
</style>
