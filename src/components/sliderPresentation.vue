<template>
  <section>
    <div class="slider">
      <div class="mobile-images slide-images" style="transform: translateX(0%)">
        <img
          class="mobile-image"
          src="@/assets/mobile/image-slide-1.jpg"
          alt="slide 1"
        />
        <img
          class="mobile-image"
          src="@/assets/mobile/image-slide-2.jpg"
          alt="slide 2"
        />
        <img
          class="mobile-image"
          src="@/assets/mobile/image-slide-3.jpg"
          alt="slide 3"
        />
      </div>

      <div class="tablet-images slide-images" style="transform: translateX(0%)">
        <img
          class="tablet-image"
          src="@/assets/tablet/image-slide-1.jpg"
          alt="slide 1"
        />
        <img
          class="tablet-image"
          src="@/assets/tablet/image-slide-2.jpg"
          alt="slide 2"
        />
        <img
          class="tablet-image"
          src="@/assets/tablet/image-slide-3.jpg"
          alt="slide 3"
        />
      </div>

      <div
        class="desktop-images slide-images"
        style="transform: translateX(0%)"
      >
        <img
          class="desktop-image"
          src="@/assets/desktop/image-slide-1.jpg"
          alt="slide 1"
        />
        <img
          class="desktop-image"
          src="@/assets/desktop/image-slide-2.jpg"
          alt="slide 2"
        />
        <img
          class="desktop-image"
          src="@/assets/desktop/image-slide-3.jpg"
          alt="slide 3"
        />
      </div>

      <div class="shadow"></div>
      <div class="inner-text">
        <h3>Lean Product Roadmap</h3>
        <p>2021 Project</p>
      </div>
    </div>
    <article>
      <h1>Brand naming & guidelines</h1>
      <div class="slider-buttons">
        <a @click.prevent="slideLeft" href="#left">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="bi bi-chevron-left"
            viewBox="0 0 16 16"
          >
            <path
              fill-rule="evenodd"
              d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"
            />
          </svg>
        </a>
        <a @click.prevent="slideRight" href="#right">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="bi bi-chevron-right"
            viewBox="0 0 16 16"
          >
            <path
              fill-rule="evenodd"
              d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z"
            />
          </svg>
        </a>
      </div>
      <img
        class="svg"
        src="@/assets/cross-display/bg-pattern-wavy-white.svg"
        alt="svg"
      />
    </article>
  </section>
</template>

<script>
export default {
  methods: {
    slideLeft() {
      // GROUPS IN HTML COLLECTION
      let slideImages = document.getElementsByClassName("slide-images");
      // IMAGES IN DESKTOP IMAGES (ALL IMAGES ARE SAME IN GROUPS)
      let imagesInSlide = document.querySelectorAll(".desktop-images img");

      // CYCLE GROUP FOR EACH MEDIA QUERY
      for (let index = 0; index < slideImages.length; index++) {
        let element = slideImages[index];

        // FIND GROUP ELEMENT TRANSLATE VALUE
        let translateNow = element.style.transform;
        let translateX = translateNow
          .replace("translateX", "")
          .replace("(", "")
          .replace(")", "")
          .replace("calc(", "")
          .replace(")", "");

        // ACTUAL GROUP TRANSLATE VALUES
        translateNow = element.style.transform;
        translateX = translateNow
          .replace("translateX", "")
          .replace("(", "")
          .replace(")", "")
          .replace("calc(", "")
          .replace(")", "");

        //LOGIC

        // TOTAL LENGTH -100 BCS STARTING FROM 0 (NEED TO BE NUMBER ! STRING)
        let totalTranslate = imagesInSlide.length * 100 - 100;
        // IF TRANSLATE IS ON START
        if (translateX == 0 + "%") {
          // JUMP ON LAST SLIDE
          element.style.transform = `translateX( ${this.numToNeg(
            totalTranslate
          )} %)`;
        } else {
          // TRANSFORM FOR EACH MEDIA QUERY TO LEFT
          element.style.transform = `translateX( calc(${translateX} + 100%))`;
        }
      }
    },
    slideRight() {
      // GROUPS IN HTML COLLECTION
      let slideImages = document.getElementsByClassName("slide-images");
      // IMAGES IN DESKTOP IMAGES (ALL IMAGES ARE SAME IN GROUPS)
      let imagesInSlide = document.querySelectorAll(".desktop-images img");

      // CYCLE GROUP FOR EACH MEDIA QUERY
      for (let index = 0; index < slideImages.length; index++) {
        let element = slideImages[index];

        // FIND GROUP ELEMENT TRANSLATE VALUE
        let translateNow = element.style.transform;
        // CLEAN translateNow TO NUMBER
        let translateX = translateNow
          .replace("translateX", "")
          .replace("(", "")
          .replace(")", "")
          .replace("calc(", "")
          .replace(")", "");

        // ACTUAL GROUP TRANSLATE VALUES
        translateNow = element.style.transform;
        translateX = translateNow
          .replace("translateX", "")
          .replace("(", "")
          .replace(")", "")
          .replace("calc(", "")
          .replace(")", "");

        //LOGIC

        // TOTAL LENGTH -100 BCS STARTING FROM 0 (NEED TO BE NUMBER ! STRING)
        let totalTranslate = imagesInSlide.length * 100 - 100;

        // IF GROUP's TRANSLATE WILL HIT END OF GROUP LIST WITH TRANSLATE
        if (translateX == this.numToNeg(totalTranslate) + "%") {
          // RESET ON START
          element.style.transform = "translateX(0%)";
        } else {
          // TRANSFORM FOR EACH MEDIA QUERY TO RIGHT
          element.style.transform = `translateX( calc(${translateX} - 100%))`;
        }
      }
    },

    numToNeg(num) {
      // FUNCTION FOR CHANGING POSITIVE NUMBER TO NEGATIVE BCS (totalTranslate is positive)
      return -Math.abs(num);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/settings.scss";

section {
  background-color: $bg-black;
  color: $white;
  position: relative;

  .shadow {
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: 5;
    top: 0;
    left: 0;
    -moz-box-shadow: inset 0px -200px 300px -200px #000;
    -webkit-box-shadow: inset 0px -200px 300px -200px #000;
    box-shadow: inset 0px -200px 300px -200px #000;
  }

  .slider {
    position: relative;
    overflow: hidden;

    .mobile-images {
      display: flex;
      flex-direction: row;
      flex-wrap: nowrap;
      transition: 0.5s ease;
    }

    img.mobile-image {
      display: block;
      min-width: 100%;
    }

    img.tablet-image {
      display: none;
    }

    img.desktop-image {
      display: none;
    }

    .inner-text {
      position: absolute;
      right: 0;
      bottom: 0;
      padding: 1.5em;
      z-index: 10;

      h1 {
        font-weight: 800;
        font-size: em(15);
      }

      p {
        font-size: em(15);
      }
    }
  }

  article {
    padding: 5em 1.5em;

    .svg {
      display: none;
    }

    h1 {
      font-size: em(32);
    }

    .slider-buttons {
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      align-items: center;
      a {
        width: max-content;
        width: 5%;
        margin-right: 2em;
        padding: 1em 1.1em;
        border: 1px solid $primary-color;
        border-radius: 9999px;

        &:hover {
          border-color: lighten($primary-color, 10%);
        }

        &:hover svg {
          fill: lighten($primary-color, 10%);
          stroke: lighten($primary-color, 10%);
        }

        svg {
          width: 100%;
          fill: $primary-color;
          stroke: $primary-color;
        }
      }
    }
  }
}

//RESPONSIVE

@media only screen and (min-width: 768px) {
  /* For tablets: */
  section {
    display: flex;
    flex-direction: row-reverse;
    justify-content: space-between;
    position: relative;
    background-color: $white;

    .slider {
      position: relative;
      display: flex;
      justify-content: flex-end;
      align-self: flex-end;
      width: 57%;

      .mobile-images {
        display: none;
      }

      .tablet-images {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        transition: 0.5s ease;
      }

      img.mobile-image {
        display: none;
      }

      img.tablet-image {
        display: block;
        min-width: 100%;
      }
      .inner-text {
        padding: 1.5rem 5rem;

        h1 {
          font-weight: 800;
          font-size: em(20);
        }

        p {
          font-size: em(18);
        }
      }
    }

    article {
      padding: 5em 2em;
      z-index: 20;
      position: absolute;
      width: 45%;
      height: max-content;
      left: 0;
      top: 0;
      background-color: $bg-black;

      .svg {
        display: block;
        width: 15%;
        position: absolute;
        top: 39%;
        right: -8%;
        z-index: 10;
      }
    }
  }
}

@media only screen and (min-width: 1440px) {
  /* For desktop: */
  section {
    .slider {
      position: relative;
      display: flex;
      justify-content: flex-end;
      align-self: flex-end;
      width: 51%;

      .mobile-images {
        display: none;
      }

      .tablet-images {
        display: none;
      }

      .desktop-images {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        transition: 0.5s ease;
      }

      img.mobile-image {
        display: none;
      }

      img.tablet-image {
        display: none;
      }

      img.desktop-image {
        display: block;
        min-width: 100%;
      }

      .inner-text {
        padding: 3rem 10rem;

        h1 {
          font-weight: 800;
          font-size: em(20);
        }

        p {
          font-size: em(18);
        }
      }
    }
    article {
      padding: 10rem;
      padding-right: 0;

      .slider-buttons {
        a {
          width: 3%;
          svg {
            width: 100%;
            fill: $primary-color;
          }
        }
      }
    }
  }
}
</style>
