<script>
export default {};
</script>

<template>
  <section class="course">
    <div class="container course_container">
      <div
        class="advantages_top"
        data-aos="fade-down"
        data-aos-duration="600"
        data-aos-delay="500"
      >
        <h2 class="advantages_title">
          <span>Advantages</span> of studying in
          <span>Mr. Abdulaziz's</span> course
        </h2>
        <p class="advantages_text">
          Skilline is one powerful online software suite that combines all the
          tools needed to run a successful school or office.
        </p>
      </div>

      <div class="courses_list">
        <div
          class="course_item"
          data-aos="fade-right"
          data-aos-duration="600"
          data-aos-delay="500"
        >
          <h3 class="course_item-title">Intensive SAT</h3>
          <a href="" class="intensive_btn"> Appy for course </a>
        </div>
        <div
          class="course_item"
          data-aos="fade-left"
          data-aos-duration="600"
          data-aos-delay="500"
        >
          <h3 class="course_item-title">CAC</h3>
          <a href="" class="intensive_btn"> Apply for CAC </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.course {
  padding-bottom: 120px;
}
.course_container {
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 60px;
}
.courses_list {
  display: flex;
  justify-content: center;
  gap: 100px;
}
.course_item {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  width: 600px;
  height: 400px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  border-radius: 20px;
}
.course_item:nth-child(1) {
  background-image: url("/images/course_intensive.png");
}
.course_item:nth-child(2) {
  background-image: url("/images/CAC.png");
}
.course_item-title {
  color: #fff;
  font-size: 26px;
  font-weight: 600;
  line-height: normal;
  margin-bottom: 18px;
}
.intensive_btn {
  padding: 24px 38px;
  border-radius: 80px;
  border: 1px solid #fff;
  color: #fff;
  font-size: 22px;
  font-weight: 500;
  line-height: normal;
  transition: all 0.3s ease-in-out;
}
.intensive_btn:hover {
  background: rgba(35, 189, 238, 0.9);
  border: 1px solid transparent;
  color: #fff;
}
</style>
