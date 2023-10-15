<script>
export default {
  data() {
    return {
      isScrolled: false,
    };
  },

  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },

  methods: {
    handleScroll(e) {
      if (window.pageYOffset > 80) {
        this.isScrolled = true;
      } else if (
        e.wheelDelta >= 0 &&
        window.pageYOffset < 80 &&
        window.pageYOffset != 0
      ) {
        this.isScrolled = true;
      } else {
        this.isScrolled = false;
      }
    },
  },
};
</script>

<template>
  <header :class="{ scrolled: isScrolled }" class="header">
    <div class="container header_container">
      <a href="#!">
        <img src="/svgs/logo.svg" alt="logo type" />
      </a>
      <div class="header_nav-list">
        <a class="header_nav-item" href="#advantages">
          <p data-text="Advantages" class="header_nav-item-txt">Advantages</p>
        </a>

        <a class="header_nav-item" href="#courses">
          <p data-text="Courses" class="header_nav-item-txt">Courses</p>
        </a>
        <a class="header_nav-item" href="#comments">
          <p data-text="Students" class="header_nav-item-txt">Students</p>
        </a>
        <a class="header_nav-item" href="#form_apply">
          <p data-text="Apply" class="header_nav-item-txt">Apply</p>
        </a>
      </div>
    </div>
  </header>
</template>

<style>
.header {
  position: fixed;
  /* top: 60px; */
  right: 0;
  left: 0;
  z-index: 9;
  padding: 15px 0;
  backdrop-filter: blur(5px);
  transition: 0.4s;
}
.header.scrolled {
  /* background: #ffffff; */
  background: rgb(255, 255, 255, 0.7);

  /* backdrop-filter: blur(10px); */
}
.header_container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.header_nav-list {
  display: flex;
  align-items: center;
  gap: 80px;
}
.header_nav-item-txt {
  transition: transform 0.3s;
  transform-origin: 50% 0;
  transform-style: preserve-3d;
  position: relative;
  display: inline-block;
  color: #252641;
  font-size: 22px;
  font-weight: 400;
  line-height: normal;
  letter-spacing: 0.44px;
}
.header_nav-item-txt::before {
  position: absolute;
  content: attr(data-text);
  transform: rotateX(-90deg);
  transform-origin: 50% 0;
  top: 100%;
  left: 0;
  width: 100%;
  height: 100%;
  color: #f48c06;
}
.header_nav-item {
  padding: 2px;
}
.header_nav-item:hover .header_nav-item-txt {
  transform: rotateX(90deg);
}
</style>
