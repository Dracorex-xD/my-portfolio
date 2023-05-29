<template lang="en">
    <div class="CallSidebar">
        <button
      class="call-sidebar"
      @mouseenter="handleMouseEnter"
      @mouseleave="handleMouseLeave"
      @click="callSidebarTruthy"
      :class="{ sidebar }"
    >
      <img src="../assets/menu.png" alt="menu icon" />
    </button>

    <heading :heading="heading" />
    <section v-if="sidebar" ref="sidebar">
      <button class="exit" @click="callSidebarTruthy">x</button>
      <side-Menu />
    </section>
    </div>
</template>
<script>
export default {
  name: "call-sidebar",
  props: {
    heading: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      sidebar: false,
      timeout: null,
      interval: null,
    };
  },

  mounted() {
    this.$el.addEventListener("mousemove", (event) => {
      this.mouseEvent = event;
    });
    // Attach keydown event listener to the window object
    window.addEventListener("keydown", this.handleKeyPress);
  },

  beforeUnmount() {
    // Remove keydown event listener when the component is unmounted
    window.removeEventListener("keydown", this.handleKeyPress);
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

    beforeDestroy() {
      clearTimeout(this.timeout);
      clearInterval(this.interval);
    },
  },
};
</script>
<style></style>
