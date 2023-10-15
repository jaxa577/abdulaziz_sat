<template>
  <transition name="slide-in">
    <div v-if="show" class="toast error-toast">
      <span>{{ message }}</span>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      message: "",
    };
  },
  methods: {
    showError(message) {
      this.message = message;
      this.show = true;
      setTimeout(() => {
        this.show = false;
      }, 3000); // Adjust the timeout as needed
    },
  },
};
</script>

<style scoped>
.error-toast {
  background-color: #f44336; /* Red background color */
  color: #fff; /* White text color */
  padding: 10px 20px;
  border-radius: 5px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 999;
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 200px;
  font-weight: bold;
}

.slide-in-enter-active,
.slide-in-leave-active {
  transition: transform 0.5s, opacity 0.5s;
}

.slide-in-enter,
.slide-in-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
</style>
