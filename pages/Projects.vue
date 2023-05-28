<template lang="en">
    <div class="container">
        <heading heading="Projects" />
        <button class="call-sidebar" @mouseenter="handleMouseEnter" @mouseleave="handleMouseLeave" @click="callSidebarTruthy" :class="{ sidebar }">

          <img src="../assets/menu.png" alt="menu icon">
        </button>
        <section v-if="sidebar" ref="sidebar">
          <button class="exit" @click="callSidebarTruthy">x</button>
          <side-Menu />
        </section>
        <div class="content">
          <section class="sub-container" id="section1">section 1</section>
          <section class="sub-container" id="section2">section 2</section>
          <section class="sub-container" id="section3">section 3</section>
          <section class="sub-container" id="section4">section 4</section>
          <section class="sub-container" id="section5">section 5</section>
          <section class="sub-container" id="section6">section 6</section>
        </div>
      <navigationBlock class="navbar" />
    </div>
</template>
<script>
export default {
  name: 'projects',
  data() {
      return {
        sidebar: false,
        timeout: null,
        interval: null
      };
    },

    methods: {
    handleKeyPress(event) {
      if (event.key === "Escape") {
        this.callSidebarTruthy();
        }
      },
    handleMouseEnter() {
      this.timeout = setTimeout(() => {
        this.callSidebarTruthy();
        this.interval = setInterval(() => {
          if (!this.isMouseOverElement(this.$el)) {
            this.handleMouseLeave();
          }
        }, 100);
      }, 3000);
    },
    handleMouseLeave() {
      clearTimeout(this.timeout);
      clearInterval(this.interval);
    },
    callSidebarTruthy() {
      this.sidebar = !this.sidebar;
    },
    isMouseOverElement(element) {
      const rect = element.getBoundingClientRect();
      const { clientX, clientY } = this.mouseEvent;
      return (
        clientX >= rect.left &&
        clientX <= rect.right &&
        clientY >= rect.top &&
        clientY <= rect.bottom
      );
    },
    mounted() {
      this.$el.addEventListener('mousemove', (event) => {
        this.mouseEvent = event;
      });
    },
    beforeDestroy() {
      clearTimeout(this.timeout);
      clearInterval(this.interval);
    }
  }
}
</script>
<style scoped>
  .content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
  }

  .sub-container {
    width: 20rem;
    height: 20rem;

  }

  .navigationBlock {
    width: 44rem;
    justify-self: center;
  }

  #section2 {
    grid-row: 1 / 3;
    grid-column: 2;
    height: 42rem;
    
  }

  #section3 {
    display: none;
  }

  #section5 {
    grid-column: 1 / 3;
    width: 44rem;
  }

  #section6 {
    display: none;
  }

  @media (min-width: 1080px) {
  .sub-container {
    width: 30rem;
    height: 30rem;
  }

  #section2 {
    height: 62rem;
  }

  #section5 {
    width: 64rem;
  }

  .navigationBlock {
    width: 64rem;
  }


}
</style>