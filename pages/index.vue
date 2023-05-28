<template>
  <div class="container" @keydown="handleKeyPress">
    <button class="call-sidebar" @mouseenter="handleMouseEnter" @mouseleave="handleMouseLeave" @click="callSidebarTruthy" :class="{ sidebar }">
      <img src="../assets/menu.png" alt="menu icon">
    </button>

    <heading heading="My-Portfolio Thing" />
    <section v-if="sidebar" ref="sidebar">
      <button class="exit" @click="callSidebarTruthy">x</button>
      <side-Menu />
    </section>
    <section class="sub-container">
      section 3 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <section class="sub-container">
      section 4 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <section class="sub-container">
      section 5 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <section class="sub-container">
      section 6 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <section class="sub-container">
      section 7 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <section class="sub-container">
      section 8 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <section class="sub-container">
      section 9 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <section class="sub-container">
      section 10 Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      provident rerum unde quis? Rerum ratione consequatur itaque ad nihil vitae ullam cum
      perferendis dolor distinctio. Voluptatum accusantium tempora quos possimus?
    </section>
    <navigationBlock class="navbar sub-container" />
  </div>
</template>

<script>

export default {
  name: "IndexPage",
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
};
</script>

<style>
</style>
