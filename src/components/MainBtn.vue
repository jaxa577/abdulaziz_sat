<script>
export default {
  props: {
    content: String,
  },
};
</script>

<template>
  <button class="main_btn">
    {{ content }}
  </button>
</template>

<style>
.main_btn {
  border-radius: 80px;
  background: #f48c06;
  border: 1px solid transparent;
  padding: 22px 38px;
  color: #fff;
  font-size: 24px;
  font-weight: 600;
  line-height: normal;
  transition: all 0.3s ease-in-out;
}
.main_btn:hover {
  background-color: transparent;
  color: #f48c06;
  border: 1px solid #f48c06;
}
</style>
