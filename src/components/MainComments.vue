<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination, Scrollbar, A11y } from "swiper/modules";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/scrollbar";
export default {
  components: {
    Swiper,
    SwiperSlide,
    Navigation,
    Pagination,
  },
};
</script>

<template>
  <section class="comments">
    <div class="container comments_container">
      <div
        data-aos="fade-right"
        data-aos-duration="600"
        data-aos-delay="500"
        class="comments_desc"
      >
        <div class="comments_desc-top">
          <span class="comments_line"></span>
          <p class="commnets_top-text">Students</p>
        </div>
        <h2 class="comments_title">What They Say?</h2>
        <p class="comments_text">
          Skilline has got more than 100k positive ratings from our users around
          the world.
          <br /><br />
          Some of the students and teachers were greatly helped by the Skilline.
          <br /><br />
          Are you too? Please give your assessment
        </p>
        <button class="comments_btn">Become a student</button>
      </div>

      <swiper
        class="swiper_comments"
        data-aos="fade-left"
        data-aos-duration="600"
        data-aos-delay="500"
        :modules="modules"
        :slides-per-view="1"
        :space-between="50"
        navigation
        :pagination="{ clickable: true }"
      >
        <swiper-slide>
          <div class="comment_item">
            <div class="comment_img">
              <img src="/images/commentator.png" alt="" />
            </div>
            <div class="comment_item-desc">
              <p class="comment_item-text">
                "Thank you so much for your help. It's exactly what I've been
                looking for. You won't regret it. It really saves me time and
                effort. Skilline is exactly what our business has been lacking."
              </p>
              <h3 class="commentator_name">Gloria Rose</h3>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="comment_item">
            <div class="comment_img">
              <img src="/images/commentator.png" alt="" />
            </div>
            <div class="comment_item-desc">
              <p class="comment_item-text">
                "Thank you so much for your help. It's exactly what I've been
                looking for. You won't regret it. It really saves me time and
                effort. Skilline is exactly what our business has been lacking."
              </p>
              <h3 class="commentator_name">Gloria Rose</h3>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="comment_item">
            <div class="comment_img">
              <img src="/images/commentator.png" alt="" />
            </div>
            <div class="comment_item-desc">
              <p class="comment_item-text">
                "Thank you so much for your help. It's exactly what I've been
                looking for. You won't regret it. It really saves me time and
                effort. Skilline is exactly what our business has been lacking."
              </p>
              <h3 class="commentator_name">Gloria Rose</h3>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="comment_item">
            <div class="comment_img">
              <img src="/images/commentator.png" alt="" />
            </div>
            <div class="comment_item-desc">
              <p class="comment_item-text">
                "Thank you so much for your help. It's exactly what I've been
                looking for. You won't regret it. It really saves me time and
                effort. Skilline is exactly what our business has been lacking."
              </p>
              <h3 class="commentator_name">Gloria Rose</h3>
            </div>
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </section>
</template>

<style>
.comments {
  /* padding-bottom: 100px; */
}
.swiper_comments {
  padding-bottom: 150px;
  padding-right: 50px;
  width: 100%;
}
.comments_container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 30px;
}
.comments_desc {
  min-width: 40%;
  max-width: 40%;
}
.comments_desc-top {
  display: flex;
  align-items: center;
  gap: 30px;
  margin-bottom: 32px;
}
.comments_line {
  width: 80px;
  height: 2px;
  display: block;
  background: #525596;
}
.commnets_top-text {
  color: #525596;
  font-size: 16px;
  font-weight: 400;
  line-height: normal;
  letter-spacing: 4px;
}
.comments_title {
  color: #2f327d;
  font-size: 50px;
  font-weight: 700;
  line-height: normal;
  margin-bottom: 30px;
}
.comments_text {
  color: #696984;
  font-size: 18px;
  font-weight: 400;
  line-height: 160%;
  letter-spacing: 0.52px;
  margin-bottom: 40px;
}
.comments_btn {
  border-radius: 80px;
  border: 1px solid #f48c06;
  padding: 23px 38px;
  color: #f48c06;
  font-size: 16px;
  font-weight: 400;
  line-height: 160%;
  letter-spacing: 0.44px;
  transition: all 0.3s ease;
}
.comments_btn:hover {
  background: #f48c06;
  color: #fff;
}
.comment_item {
  position: relative;
}
.comment_img {
  /* width: 560px;
  height: 700px; */
}
.comment_img img {
  width: 560px;
  height: 700px;
  object-fit: cover;
  object-position: center;
  border-radius: 20px;
}
.comment_item-desc {
  max-width: 80%;
  position: absolute;
  right: 0;
  bottom: -100px;
  border-radius: 20px;
  background: #fff;
  box-shadow: 2px 4px 60px 0px rgba(41, 44, 124, 0.1);
  border-left: 14px solid #f67766;
  padding: 42px;
}
.comment_item-text {
  color: #5f5f7e;
  font-size: 18px;
  font-weight: 400;
  line-height: 180%;
  letter-spacing: 0.44px;
  padding-left: 32px;
  border-left: 1px solid #bdbdd1;
  margin-bottom: 32px;
}
.commentator_name {
  padding-left: 32px;
  color: #5f5f7e;
  font-size: 22px;
  font-weight: 600;
  line-height: 180%;
}
.swiper-button-prev,
.swiper-button-next {
  width: 80px !important;
  height: 80px !important;
  background: #fff !important;
  border-radius: 50% !important;
  box-shadow: 2px 4px 60px 0px rgba(41, 44, 124, 0.1) !important;
}
.swiper-button-next {
  right: 50px !important;
}
.swiper-button-prev {
  left: 0 !important;
}
.swiper-button-prev:after,
.swiper-button-next:after {
  font-weight: 700;
}
.swiper-button-prev:after {
  margin-right: 5px;
}
.swiper-button-next:after {
  margin-left: 5px;
}
</style>
