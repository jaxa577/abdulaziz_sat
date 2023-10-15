<script>
export default {
  props: {
    curValue: String,
    selectList: Array,
    defaultValue: String,
    invalid: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      isSelectOpened: false,
      selectedValue: this.defaultValue,
    };
  },

  mounted() {
    setTimeout(() => {
      this.validateOnMount();
    }, 300);
  },
  methods: {
    closeSelectOnOutsideClick(event) {
      if (!this.$el.contains(event.target)) {
        this.isSelectOpened = false;
        window.removeEventListener("click", this.closeSelectOnOutsideClick);
        this.scrollToTop();
      }
    },

    validateOnMount() {
      if (this.curValue) {
        let givenItem = this.selectList.find(
          (item) => item.id == this.curValue
        );
        this.selectedValue = givenItem.name;
      }
    },
    openSelect() {
      this.isSelectOpened = !this.isSelectOpened;
      if (this.isSelectOpened) {
        window.addEventListener("click", this.closeSelectOnOutsideClick);
      } else {
        window.removeEventListener("click", this.closeSelectOnOutsideClick);
      }
      this.scrollToTop();
    },
    setOption(option) {
      this.selectedValue = option.name;
      this.$emit("getSelectInfo", option.name);
      // this.scrollToTop();
    },
    scrollToTop() {
      const scrollableDiv = this.$refs.selectDiv;
      if (scrollableDiv) {
        scrollableDiv.scrollTop = 0;
      }
    },
  },
  //   watch: {
  //     curValue: {
  //       immediate: true,
  //       handler: function () {
  //         if (this.curValue) {
  //           this.invalid = false;
  //           this.validateOnMount();
  //         } else {
  //           this.invalid = true;
  //           this.selectedValue = this.defaultValue;
  //           this.$forceUpdate();
  //         }
  //       },
  //     },
  //   },
};
</script>

<template>
  <div class="select_holder">
    <div
      class="select_wrapper"
      @click="openSelect"
      :class="{ active: isSelectOpened, invalid: invalid }"
      :invalid="invalid"
    >
      <div class="select_list-item current">
        <p>
          {{ selectedValue }}
        </p>
        <img
          class="custom_select-arrow"
          src="/svgs/arrow-bottom.svg"
          width="18"
        />
      </div>
      <div
        :class="{ active: isSelectOpened }"
        ref="selectDiv"
        class="select_list"
      >
        <div
          v-for="(option, index) in selectList"
          class="select_list-item"
          @click="setOption(option)"
          @invalid="invalid = false"
          :class="{ selected: selectedValue == option.name }"
          :key="`option${index}`"
        >
          {{ option?.name }}
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.select_holder {
  position: relative;
  height: 71px;
  /*   width: 250px; */
}

.select_wrapper {
  position: absolute;
  z-index: 9999;
  top: 0;
  left: 0;
  right: 0;
  border-radius: 10px;
  border: 1px solid #83839a;
  background: var(--5, #fff);
  cursor: pointer;
  max-height: 71px;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  padding-bottom: 2px;
  user-select: none;
  transition: 0.5s;
}
.select_wrapper.active {
  max-height: 250px;
  overflow: visible;
  border-color: #26c1f2;
  z-index: 99;
  border-radius: 10px;
}
/* .select_wrapper.invalid {
  border: 1px solid #ff3333;
} */
.select_list {
  width: 100%;
  padding: 10px 0;
  border-radius: 10px;
  background: var(--5, #fff);
  max-height: 200px;
  overflow-y: scroll;
  z-index: 9999;
}
.select_list::-webkit-scrollbar {
  width: 5px;
}

.select_list::-webkit-scrollbar-thumb {
  background: #26c1f2;
  border-radius: 6px;
  transition: all 0.3s ease;
}

.select_list::-webkit-scrollbar-thumb:hover {
  background: rgba(244, 140, 6, 0.5);
}

.select_list::-webkit-scrollbar-track {
  background: #b2b3cf;
  border-radius: 10px;
}
.select_list-item {
  width: 100%;
  padding: 10px 14px;
  color: #696984;
  font-size: 14px;
  font-weight: 400;
  line-height: 160%;
  letter-spacing: 0.44px;
  transition: all 0.3s ease;
}
.select_list-item:hover {
  background: rgba(38, 193, 242, 0.5);
  color: #fff;
}
.select_list-item.selected {
  /* background: #fbecd7; */
  color: #fff;
  background: rgba(38, 193, 242, 0.5);
}
.select_list-item.current {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 20px;
  height: 71px;
  padding: 0 14px;
  display: flex;
  align-items: center;
  flex-shrink: 0;
}
.select_list-item.current p {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
.select_list-item.current:hover {
  background: none !important;
  color: #606060 !important;
}
.custom_select-arrow {
  transition: all 0.3s ease;
}
.select_wrapper.active .custom_select-arrow {
  transform: rotate(-180deg);
}
</style>
