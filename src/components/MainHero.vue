<script>
import mainBtn from "./MainBtn.vue";
import { KinesisContainer, KinesisElement } from "vue-kinesis";
import Parallax from "parallax-js";
export default {
  components: {
    mainBtn,
    KinesisElement,
    KinesisContainer,
  },
  data() {
    return {
      appearingItems: [
        {
          name: "More than 250",
          text: "Assisted Student",
          img: "/svgs/calendar.svg",
          active: false,
          // afterActivate: false,
        },
        {
          name: "More than 250",
          text: "Assisted Student",
          img: "/svgs/calendar.svg",
          active: false,
          // afterActivate: false,
        },
        {
          name: "More than 250",
          text: "Assisted Student",
          img: "/svgs/calendar.svg",
          active: false,
          // afterActivate: false,
        },
      ],
    };
  },
  mounted() {
    this.manageAppearing();
  },
  methods: {
    manageAppearing() {
      for (let index = 0; index < this.appearingItems.length; index++) {
        setTimeout(() => {
          this.$refs.heroItem[index].classList.add("active");
          this.appearingItems[index].active = true;
        }, index * 800);
      }
      for (let index = 0; index < this.appearingItems.length; index++) {
        setTimeout(() => {
          this.$refs.heroItem[index].classList.add("activated");
          // this.appearingItems[index].active = true;
        }, this.appearingItems.length * 800);
      }
    },
  },
};
</script>

<template>
  <section class="hero">
    <div class="container hero_container">
      <div class="hero_info">
        <h2 class="hero_tite">
          Studying <span>SAT</span> with <span>Mr.Abdulaziz</span> is much
          easier
        </h2>
        <p class="hero_text">
          Skilline is an interesting platform that will teach you in more an
          interactive way
        </p>
        <div class="hero_btns">
          <mainBtn content="Join for free" />
        </div>
      </div>

      <div class="hero_example">
        <img class="hero_img" src="/images/hero_bckg.png" alt="" />
        <div class="appearing_els">
          <div
            v-for="appItem in appearingItems"
            ref="heroItem"
            class="appearing_item"
            :class="{ active: appItem.active }"
          >
            <img :src="appItem.img" alt="" />
            <div>
              <h3 class="apearing_item-title">{{ appItem.name }}</h3>
              <p class="apearing_item-text">{{ appItem.text }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.hero {
  padding-top: 200px;
  background-color: #fbecd7;
  /* border-bottom-left-radius: 100px;
  border-bottom-right-radius: 100px; */
  height: calc(100vh + 20px);
}
.container {
}
.hero_container {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 80px;
}
.hero_info {
  width: 50%;
  padding-top: 50px;
}
.hero_tite {
  color: #2f327d;
  font-size: 48px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  margin-bottom: 34px;
}
.hero_tite span {
  color: #f48c06;
  font-size: 48px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}
.hero_text {
  color: #464646;
  font-size: 22px;
  font-style: normal;
  font-weight: 400;
  line-height: 160%; /* 38.4px */
  margin-bottom: 52px;
}
.hero_btns {
}
.hero_example {
  width: 55%;
  position: relative;
}
.hero_img {
  position: absolute;
  top: -150px;
  left: 50%;
  transform: translateX(-50%);
}
.appearing_item {
  position: absolute;
  display: flex;
  align-items: center;
  gap: 32px;
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(10px);
  padding: 15px 28px;
  transform: scale(0);
}
.appearing_item:nth-child(1) {
  top: 130px;
  left: -100px;
}
.appearing_item:nth-child(2) {
  top: 350px;
  right: -150px;
}
.appearing_item:nth-child(3) {
  top: 500px;
  left: -50px;
}
.apearing_item-title {
  color: #595959;
  font-size: 24px;
  font-weight: 500;
  line-height: 180%; /* 43.2px */
  letter-spacing: 0.48px;
}
.apearing_item-text {
  color: #545567;
  font-size: 20px;
  font-weight: 400;
  line-height: 180%; /* 36px */
  letter-spacing: 0.4px;
}

.appearing_item.active {
  -webkit-animation: scale-up-center 0.6s cubic-bezier(0.39, 0.575, 0.565, 1)
    both;
  animation: scale-up-center 0.6s cubic-bezier(0.39, 0.575, 0.565, 1) both;
}
.appearing_item.active.activated {
  animation: breathing 4s infinite alternate;
}
@-webkit-keyframes scale-up-center {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}
@keyframes scale-up-center {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}

@keyframes breathing {
  0% {
    transform: scale(1) rotate(0deg);
  }
  50% {
    transform: scale(0.95) rotate(-1deg);
  }
  100% {
    transform: scale(1.05) rotate(1deg);
  }
}

@media only screen and (max-width: 1540px) {
  .hero {
    padding-top: 120px;
  }
  .hero_info {
    padding: 0;
  }
  .hero_img {
    height: 750px;
    top: -120px;
  }
  .appearing_item:nth-child(1) {
    top: 0;
  }
  .appearing_item:nth-child(2) {
    top: 150px;
    right: -85px;
  }
  .appearing_item:nth-child(3) {
    top: 250px;
  }
  .apearing_item-title {
    font-size: 20px;
  }
  .apearing_item-text {
    font-size: 14px;
  }
}
</style>
