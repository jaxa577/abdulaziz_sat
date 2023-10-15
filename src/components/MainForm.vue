<script>
import customSelect from "./CustomSelect.vue";
import mainBtn from "./MainBtn.vue";
import errorToast from "./ErrorToast.vue";
import greenToast from "./GreenToast.vue";
export default {
  components: {
    customSelect,
    mainBtn,
    errorToast,
    greenToast,
  },
  data() {
    return {
      englishLevels: [
        {
          id: 1,
          name: "Beginner (A1)",
        },
        {
          id: 2,
          name: "Elementary (A2)",
        },
        {
          id: 3,
          name: "Pre-Intermediate (B1)",
        },
        {
          id: 4,
          name: "Intermediate (B2)",
        },
        {
          id: 5,
          name: "Upper Intermediate (C1)",
        },
      ],
      mathLevels: [
        {
          id: 1,
          name: "Elementary School Math",
        },
        {
          id: 2,
          name: "Middle School Math",
        },
        {
          id: 3,
          name: "High School Math",
        },
        {
          id: 4,
          name: "Advanced High School Math",
        },
      ],
      fullName: null,
      age: null,
      englishLevel: null,
      mathLevel: null,
      number: null,
      tgUserName: null,
      additionalMess: null,
    };
  },

  methods: {
    postForm() {
      if (!this.fullName) {
        this.$refs.errorToast.showError("Please enter your 'Full name'!");
      } else if (!this.age) {
        this.$refs.errorToast.showError("Please enter your 'Age'!");
      } else if (!this.englishLevel) {
        this.$refs.errorToast.showError("Please choose your 'English level'!");
      } else if (!this.mathLevel) {
        this.$refs.errorToast.showError("Please choose your 'Math level'!");
      } else if (!this.number) {
        this.$refs.errorToast.showError("Please enter your 'Phone number'!");
      } else if (!this.tgUserName) {
        this.$refs.errorToast.showError(
          "Please enter your 'Telegram user-name'!"
        );
      } else if (!this.additionalMess) {
        this.$refs.errorToast.showError("Please enter 'Additional message'!");
      } else {
        fetch(`https://abdulaziz-bot.onrender.com/send`, {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({
            todos: this.fullName,
            fio: this.age,
            startDate: this.englishLevel,
            endDate: this.mathLevel,
            hourly: this.number,
            userName: this.tgUserName,
            addMessage: `\n ${this.additionalMess}`,
          }),
        }).then((res) => {
          this.$refs.greenToast.showSuccess(
            "Your details have been successfully sent!"
          );
        });
      }
    },

    getMath(name) {
      this.mathLevel = name;
    },
    getEngl(name) {
      this.englishLevel = name;
    },
  },
};
</script>

<template>
  <errorToast ref="errorToast" />
  <greenToast ref="greenToast" />
  <section id="form_apply" class="form">
    <div class="container form_container">
      <div
        class="advantages_top"
        data-aos="fade-down"
        data-aos-duration="600"
        data-aos-delay="500"
      >
        <h2 class="advantages_title">
          Apply to <span>Mr. Abdulaziz's</span> course
        </h2>
        <p class="advantages_text">
          Prepare for success with our comprehensive SAT course - boost your
          scores and unlock college opportunities.
        </p>
      </div>
      <div class="input_rows-list">
        <div
          class="form_inputs-row"
          data-aos="fade-left"
          data-aos-duration="600"
          data-aos-delay="500"
        >
          <div class="form_input-item">
            <label for="full_name">Full name</label>
            <input
              v-model="fullName"
              type="text"
              placeholder="Enter your full name"
              id="full_name"
            />
          </div>
          <div class="form_input-item">
            <label for="age">Age</label>
            <input
              v-model="age"
              type="text"
              placeholder="Enter your age"
              id="age"
            />
          </div>
        </div>

        <div
          class="form_inputs-row"
          data-aos="fade-left"
          data-aos-duration="600"
          data-aos-delay="500"
        >
          <div class="form_input-item">
            <label for="phone_num">Phone number</label>
            <input
              v-model="number"
              type="text"
              placeholder="+998999999999"
              id="phone_num"
            />
          </div>
          <div class="form_input-item">
            <label for="tg_user-name">Telegram user-name</label>
            <input
              type="email"
              v-model="tgUserName"
              placeholder="Enter your telegram user-name"
              id="tg_user-name"
            />
          </div>
        </div>

        <div
          class="form_inputs-row select"
          data-aos="fade-right"
          data-aos-duration="600"
          data-aos-delay="500"
        >
          <customSelect
            class="form_main-select"
            defaultValue="Choose your english level"
            @getSelectInfo="getEngl"
            :selectList="englishLevels"
            :curValue="englishLevel"
          />

          <customSelect
            class="form_main-select"
            defaultValue="Choose your math level"
            @getSelectInfo="getMath"
            :selectList="mathLevels"
            :curValue="mathLevel"
          />
        </div>

        <div
          class="form_inputs-row text-area"
          data-aos="fade-right"
          data-aos-duration="600"
          data-aos-delay="500"
        >
          <label for="additional_comment"
            >Additional message to Mr. Abdulaziz</label
          >
          <textarea
            id="additional_comment"
            placeholder="Enter your message"
            cols="30"
            rows="10"
            v-model="additionalMess"
          ></textarea>
        </div>
        <button
          data-aos="fade-right"
          data-aos-duration="600"
          data-aos-delay="500"
          class="intensive_btn form"
          @click="postForm"
        >
          Appy for course
        </button>
      </div>
    </div>
  </section>
</template>

<style>
.form {
  /* background: rgba(37, 38, 65, 1); */
  padding: 30px 0;
  margin-bottom: 50px;
}
.form_container {
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 30px;
}
.input_rows-list {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.form_inputs-row {
  display: flex;
  width: 100%;
  align-items: center;
  gap: 20px;
}
.form_inputs-row.text-area {
  flex-direction: column;
  align-items: flex-start;
}
.form_main-select {
  width: 100%;
}
.form_input-item {
  display: flex;
  flex-direction: column;
  gap: 5px;
  width: 100%;
}

.form_input-item input {
  width: 100%;
  padding: 20px 14px;
  border-radius: 10px;
  border: 1px solid #83839a;
  color: #696984;
  font-size: 18px;
  font-weight: 400;
  line-height: 160%;
  letter-spacing: 0.44px;
  transition: all 0.3s ease;
}
.form_input-item input:focus {
  border: 1px solid #26c1f2;
}
.form_input-item label,
.form_inputs-row label {
  color: #252641;
  font-size: 16px;
  font-weight: 500;
  line-height: normal;
  letter-spacing: 0.88px;
}
.form_inputs-row textarea {
  width: 100%;
  padding: 20px 14px;
  border-radius: 10px;
  border: 1px solid #83839a;
  resize: none;
  color: #696984;
  font-size: 14px;
  font-weight: 400;
  line-height: 160%;
  letter-spacing: 0.44px;
  transition: all 0.3s ease;
}
.form_inputs-row textarea:focus {
  border-color: #26c1f2;
}
.form_inputs-row.select {
  position: relative;
  z-index: 999;
}
.apply_btn {
  width: fit-content;
  padding: 10px 30px;
  font-size: 16px;
}
.intensive_btn.form {
  padding: 24px 37px;
  width: fit-content;
  background: rgba(35, 189, 238, 0.9);
  border: 1px solid #26c1f2;
  color: #fff;
  transition: all 0.3s ease !important;
}
.intensive_btn.form:hover {
  /* border: 1px solid #26c1f2; */
  color: #26c1f2;
  background: #fff;
}
</style>
