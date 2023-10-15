<script></script>

<template>
  <section class="advantages">
    <div class="container advantages_container">
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
      <div class="advantages_list">
        <div
          data-aos="fade-right"
          data-aos-duration="500"
          data-aos-delay="500"
          class="advantages_list-item"
        >
          <div class="advantages_item-icon">
            <img src="/svgs/file-invoice.svg" alt="" />
          </div>
          <h3 class="advantages_item-title">
            Online Billing, Invoicing, & Contracts
          </h3>
          <p class="advantages_item-text">
            Simple and secure control of your organization's financial and legal
            transactions. Send customized invoices and contracts
          </p>
        </div>
        <div
          data-aos="fade-right"
          data-aos-duration="500"
          data-aos-delay="500"
          class="advantages_list-item"
        >
          <div class="advantages_item-icon">
            <img src="/svgs/calendar_itself.svg" alt="" />
          </div>
          <h3 class="advantages_item-title">
            Online Billing, Invoicing, & Contracts
          </h3>
          <p class="advantages_item-text">
            Simple and secure control of your organization's financial and legal
            transactions. Send customized invoices and contracts
          </p>
        </div>
        <div
          data-aos="fade-right"
          data-aos-duration="500"
          data-aos-delay="500"
          class="advantages_list-item"
        >
          <div class="advantages_item-icon">
            <img src="/svgs/users.svg" alt="" />
          </div>
          <h3 class="advantages_item-title">
            Online Billing, Invoicing, & Contracts
          </h3>
          <p class="advantages_item-text">
            Simple and secure control of your organization's financial and legal
            transactions. Send customized invoices and contracts
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.advantages {
  width: 100%;
  margin-top: 120px;
  padding-bottom: 120px;
}
.container {
}
.advantages_container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 160px;
}
.advantages_top {
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 20px;
  width: 75%;
}
.advantages_title {
  color: #2f327d;
  font-size: 36px;
  font-weight: 700;
  line-height: 180%; /* 64.8px */
}
.advantages_title span {
  color: #f48c06;
}
.advantages_text {
  color: #696984;
  text-align: center;
  font-size: 24px;
  font-weight: 400;
  line-height: 180%; /* 43.2px */
}
.advantages_list {
  display: flex;
  justify-content: space-between;
  gap: 60px;
  width: 100%;
}
.advantages_list-item {
  position: relative;
  width: calc(333% - 40px);
  padding: 122px 36px 50px 36px;
  border-radius: 20px;
  background: #fff;
  box-shadow: 0px 10px 60px 0px rgba(38, 45, 118, 0.08);
}
.advantages_item-icon {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100px;
  height: 100px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.advantages_list-item:nth-child(1) .advantages_item-icon {
  background-color: #5b72ee;
}
.advantages_list-item:nth-child(2) .advantages_item-icon {
  background-color: #f48c06;
}
.advantages_list-item:nth-child(3) .advantages_item-icon {
  background-color: #29b9e7;
}
.advantages_item-title {
  color: #2f327d;
  text-align: center;
  font-size: 26px;
  font-weight: 500;
  line-height: normal;
  margin-bottom: 24px;
}
.advantages_item-text {
  color: #696984;
  text-align: center;
  font-size: 16px;
  font-weight: 400;
  line-height: 180%; /* 36px */
}
</style>
