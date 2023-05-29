<template>
  <Nuxt />
</template>

<script>
export default {
  name: 'DefaultLayout',

}

</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@300&display=swap");

/*
    1. Use a more-intuitive box-sizing model.
  */
*,
*::before,
*::after {
  box-sizing: border-box;
}

/*
    2. Remove default margin
  */
* {
  margin: 0;
}

/*
    3. Allow percentage-based heights in the application
  */
html,
body {
  height: 100%;
}

/*
    Typographic tweaks!
    4. Add accessible line-height
    5. Improve text rendering
  */
body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}

/*
    6. Improve media defaults
  */
img,
picture,
video,
canvas,
svg {
  display: block;
  max-width: 100%;
}

/*
    7. Remove built-in form typography styles
  */
input,
button,
textarea,
select {
  font: inherit;
}

/*
    8. Avoid text overflows
  */
p,
h1,
h2,
h3,
h4,
h5,
h6 {
  overflow-wrap: break-word;
}

/*
    9. Create a root stacking 
    context
  */
#root,
#__next {
  isolation: isolate;
}

:root {
  --text-color: #4ebec6;
  --background-color: #e9bbe5;
  --primary-button-color: #61d1eb;
  --secondary-button-color: #ba4be9;
  --accent-color: #de60df;
}

body {
  background-color: var(--secondary-button-color);
}

.container {
  height: 200vh;
  background: url("../assets/background.png") no-repeat top center / cover;
  display: grid;
  grid-template-rows: repeat(14, 1fr);
  font-family: inter, sans-serif;
  color: var(--text-color);
  z-index: -10;
  box-shadow: inset 0 0 3rem var(--accent-color);
  text-align: center;

}

.sub-container {
  height: fit-content;
  margin: 1rem;
  background-color: var(--background-color);
  opacity: 0.9;
  width: 90%;
  border-radius: 0.3rem;
  text-align: left;
  display: flex;
  justify-self: center;
  padding: 1rem;
  border-bottom: 0.1rem var(--accent-color) solid;
  box-shadow: 0 0 10px var(--accent-color);
}

.navbar {
  background-color: var(--primary-button-color);
  margin: 0;
  border-radius: 0.3rem;
  opacity: 1;
  padding: 1rem;
  width: 90%;


}

.navigationBlock {
  width: 46rem;
  justify-self: center;
  width: 90%;

}

.standard {
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  background-color: none;
}

.call-sidebar {
  background-color: #00000000;
  color: var(--secondary-button-color);
  padding: 0.5rem;
  font-size: 0.8rem;
  font-weight: 600;
  position: absolute;
  border: none;
  top: 0;
  right: 0;
  outline: none;
  margin: 1rem;
  margin-top: 2.2rem;

}

.call-sidebar:hover {
  transform: rotateZ(-270deg);
  transition: 0.5s;
}

.call-sidebar>img {
  height: 3rem;

}

.exit {
  z-index: 11;
  top: 0;
  right: 33vw;
  position: fixed;
  background-color: #00000000;
  outline: none;
  border: none;
  color: var(--secondary-button-color);
}


::-webkit-scrollbar {
  display: none;
}

@media (min-width: 1080px) {
  body {
    background-color: var(--secondary-button-color);
    justify-content: center;
    display: flex;
  }

  .container {
    background: url("../assets/background.png") no-repeat top center;
    width: 1080px;

  }

  .sub-container {
    width: 65rem;
  }

  .call-sidebar {
    border-radius: 0.3rem;
    right: 15vw;
  }

  .heading {
    margin-bottom: none;
    padding: 10px;

  }

  .sidebar-menu>.heading {
    box-shadow: none;
    border-radius: none;
  }
}
</style>