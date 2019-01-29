<template>
  <div id="app">
    <div id="menu">
      <ul id="menu-list">
        <li title="About">
          <a class="menu-link" id="about-link" data-link-to="about-slide">
            <i class="material-icons">sentiment_satisfied_alt</i>
          </a>
        </li>
        <li title="Work">
          <a class="menu-link" id="work-link" data-link-to="work-slide">
            <i class="material-icons">work</i>
          </a>
        </li>
        <li title="Not Work">
          <a class="menu-link" id="notwork-link" data-link-to="notwork-slide">
            <i class="material-icons">category</i>
          </a>
        </li>
        <li title="Contact">
          <a class="menu-link" id="contact-link" data-link-to="contact-slide">
            <i class="material-icons">email</i>
          </a>
        </li>
      </ul>
    </div>
    <section id="title-slide" class="slide">
      <h1>TRUMAN</h1>
    </section>
    <section id="about-slide" class="slide">
      <h1>💻 🐕 🍪 🎮 🎃 🗺 🎧 🏖 🎨 🥐 🦇</h1>
      <p>
        I’m a curious and creative visual engineer and problem solver, always looking to build things that look better and think smarter!
      </p>
      <p>
        Currently working for <a class="underline" href="https://verbalplusvisual.com/" title="Verbal + Visual" target="_blank">Verbal + Visual</a> as a Full Stack Developer, crafting considered e-commerce experiences for thoughtful brands.
      </p>
    </section>
    <section id="work-slide" class="slide">
      <h1>Work</h1>
      <div id="work-grid" class="grid">
        <div id="work-grid-card-0" class="grid-card">
          <img id="work-grid-card-0-img"
            class="grid-card-img"
            src="https://gradientjoy.com/400x400?id=22"
            alt="">
          <h2 id="work-grid-card-0-header"
            class="grid-card-header">
            Milly
          </h2>
          <p id="work-grid-card-0-desc"
            class="grid-card-desc">
            Migrated from Magento to Shopify+, rebuilt and optimzed frontend experience, simplified admin process
          </p>
        </div>
        <div id="work-grid-card-1" class="grid-card">
          <img id="work-grid-card-1-img"
            class="grid-card-img"
            src="https://gradientjoy.com/400x400?id=33"
            alt="">
          <h2 id="work-grid-card-1-header"
            class="grid-card-header">
            The Sak & SakRoots
          </h2>
          <p id="work-grid-card-1-desc"
            class="grid-card-desc">
            Redesigned website and CMS structure, combining 2 brands under one Shopify+ ecosystem
          </p>
        </div>
      </div>
    </section>
    <section id="notwork-slide" class="slide">
      <h1>Not Work</h1>
    </section>
    <section id="contact-slide" class="slide">
      <h1>Contact</h1>
    </section>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';

const d = document;
// const w = window;

d.addEventListener('DOMContentLoaded', () => {
  const menuLinkArr = Array.from(d.getElementsByClassName('menu-link'));
  menuLinkArr.forEach((link) => {
    link.addEventListener('click', () => {
      console.log(link);
      const linkSlide = d.getElementById(link.dataset.linkTo);
      linkSlide.scrollIntoView({ behavior: 'smooth' });
    });
  });
  // const slideArr = Array.from(d.getElementsByClassName('slide'));
});

export default {
  name: 'app',
  components: {
    // HelloWorld,
  },
};
</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css?family=Catamaran:400,700,900');
@import url('https://fonts.googleapis.com/icon?family=Material+Icons');

// START Reset
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
notworkicle, aside, canvas, details, embed,
figure, figcaption, footer, header, hgroup,
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
// END Reset

$catamaran: 'Catamaran', sans-serif;

$orange: #F9C300;
$brown: #D89782;

$green: #00FA9A;
$blue: #77C5F9;
$dark-blue: #6DB4E3;

$yellow: #F9F100;
$purple: #C495F9;

$red: #F90049;
$pink: #F995BF;

$black: #041B15;
$white: #F1F7ED;

$shadow: rgba($black, .3);


body {
  background-color: $black;
  font-family: $catamaran;
  font-size: 1.2rem;
  color: $white;
}

h1 {
  font-weight: 900;
  font-size: 5vw;
}

a {
  color: $white;
  text-decoration: none;

  &.underline {
    position: relative;
    display: inline-block;
    z-index: 1;
    transition: transform .3s;
    &::before {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      transform: translateY(-3px);
      height: 2px;
      width: 100%;
      background-color: $white;
      transition: height .3s, background-color .3s, transform .3s;
      z-index: -1;
    }

    &:hover {
      transform: scale(1.05);
      &::before {
        transform: scaleX(1.06);
        height: 100%;
        background-color: rgba($black, .1);
      }
    }
  }


}

.material-icons {
  font-size: 2rem;
}

#app {
  height: 100vh;
  width: 100vw;
}

#menu {
  position: fixed;
  top: 3%;
  left: 0;
  width: 100%;
  z-index: 3;
  transform: translateY(-10%);

  @media only screen and (min-width: 1100px) {
    left: 3vw;
    top: 50%;
    transform: translateY(-50%);
    width: auto;
  }

  #menu-list {
    list-style: none;
    display: flex;
    justify-content: space-around;
    width: 100%;

    @media only screen and (min-width: 1100px) {
      display: block;
      width: auto;
    }

    .menu-link {
      cursor: pointer;
      .material-icons {
        color: $white;
        font-size: 7vh;
        transition: color .3s, transform .3s;

        &:hover {
          transform: scale(1.05);
          text-shadow: .2 .2 .2 $shadow;
        }
      }

      &#about-link {
        &:hover {
          .material-icons{
            color: $green;
          }
        }
      }

      &#work-link {
        &:hover {
          .material-icons {
            color: $orange;
          }
        }
      }

      &#notwork-link {
        &:hover {
          .material-icons {
            color: $yellow;
          }
        }
      }

      &#contact-link {
        &:hover {
          .material-icons {
            color: $red;
          }
        }
      }
    }
  }
}

.slide {
  position: relative;
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  &#title-slide {
    background-color: $blue;

    h1 {
      color: $green;
      font-size: 15vw;
    }
  }

  &#about-slide {
    background-color: $blue;

    h1 {
      color: $green;
      margin: 2% 0;

      @media only screen and (min-width: 550px) {
        margin: 0;
      }
    }

    p {
      width: 75%;
      max-width: 500px;
      padding: 2% 2% 0;
      font-size: 1.3rem;
      font-weight: 700;
      text-align: center;
    }
  }

  &#work-slide {
    background-color: $brown;

    h1 {
      color: $orange;
      margin: 5% 0;

      @media only screen and (min-width: 550px) {
        margin: 0;
      }
    }
  }

  &#notwork-slide {
    background-color: $purple;

    h1 {
      color: $yellow;
    }
  }

  &#contact-slide {
    background-color: $pink;

    h1 {
      color: $red;
    }
  }
}

.grid {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 100%;

  &-card {
    flex-basis: 50%;
    padding: 2% 2% 0;
    transition: transform .3s;
    cursor: pointer;

    &:hover {
      transform: scale(1.05);
    }

    @media only screen and (min-width: 550px) {
      flex-basis: 40%;
    }

    @media only screen and (min-width: 825px) {
      flex-basis: 30%;
    }

    @media only screen and (min-width: 1100px) {
      flex-basis: 20%;
    }

    &-img {
      max-width: 100%;
      max-height: 100%;
    }

    &-header {
      display: none;
      text-transform: uppercase;
      font-weight: 700;
      text-align: center;

      @media only screen and (min-width: 825px) {
        text-align: left;
      }

      @media only screen and (min-width: 550px) {
        display: block;
        font-size: 1.5rem;
      }
    }

    &-desc {
      display: none;
      font-size: 1rem;

      @media only screen and (min-width: 825px) {
        display: block;
      }
    }
  }
}

</style>
