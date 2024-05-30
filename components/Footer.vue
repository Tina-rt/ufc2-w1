<template>
  <div class="footer w-full flex flex-col items-center justify-center bg-[#351E39]  py-10">
    <div class="w-full flex items-center justify-between">
      <Logo :invert="true" />
      <div class="socials flex items-center gap-5 text-white text-2xl">
        <i class="pi pi-instagram"></i>
        <i class="pi pi-twitter"></i>
        <i class="pi pi-facebook"></i>
        <i class="pi pi-linkedin"></i>
        <i class="pi pi-youtube"></i>
      </div>
    </div>
    <div class="footer-links items-start text-white w-full mt-10">
      <div class="footer-header">
        <div class="">
          Useful Links
        </div>
        <div class="">
          Services
        </div>
        <div class="hidden md:block lg:block">
          Contact Us
        </div>
        <div class="dropdown-icon">
          <i class="pi pi-chevron-down"></i>
        </div>
      </div>
      <div class="footer-section-1 flex flex-col gap-2 items-start">
        <ul>
          <li>Services</li>
          <li>Testimonials</li>
          <li>Products</li>
          <li>Resources</li>
          <li>Pricing</li>
        </ul>
      </div>
      <div class="footer-section-2 flex flex-col gap-2 items-start">
        <ul>
          <li>Drones</li>
          <li>Discounts</li>
          <li>Drones Discount</li>
          <li>News</li>
          <li>Information</li>
        </ul>
      </div>
      <div class="footer-section-3 flex w-full flex-col lg:flex-row md:flex-row gap-2 items-start">
        <div class="contact-info flex flex-col gap-5 w-full">
          <div class="card-border-gradient w-full">
            Jamma Masjid Galli Ward No2
          </div>
          <div class="card-border-gradient flex flex-col w-full">
            <span>+91 98102 123456</span>
            <span>profile@jammamasjid.com</span>
          </div>
        </div>
        <div class="w-full h-full">
  
          <div class="image-container h-full rounded-lg p-2">
          </div>
        </div>
      </div>
    </div>
    <!-- <table class="footer-table text-white w-full mt-10">
      <tr class="">
        <th>Usefull Links</th>
        <th>Services</th>
        <th>Contact Us</th>
      </tr>
      <tr>
        <td class="">Services</td>
        <td>Drones</td>
        <td rowspan="2">
          <div class="card-border-gradient">
            Jamma Masjid Galli Ward No2
          </div>
        </td>
        <td rowspan="5">
          <div class="image-container rounded-lg p-2">
          </div>
        </td>
      </tr>
      <tr>
        <td>Testimonials</td>
        <td>Discounts</td>
      </tr>
      <tr>
        <td>Products</td>
        <td>Drones Discount</td>
        <td rowspan="3">
          <div class="card-border-gradient flex flex-col">
            <span>+91 98102 123456</span>
            <span>profile@jammamasjid.com</span>
          </div>
        </td>
      </tr>
      <tr>
        <td>Resources</td>
        <td>News</td>
      </tr>
      <tr>
        <td>Pricing</td>
        <td>Information</td>
      </tr>
    </table> -->
  </div>
</template>

<script lang="ts" setup>
import 'primeicons/primeicons.css'
</script>

<style lang="scss" scoped>
.footer {
  padding: 40px 80px;

  @media (max-width: 768px) {
    padding: 20px;
  }
  .footer-links{
    display: grid;
    grid-template-areas: "header header header header"
    "section-1 section-2 section-3 section-3"
    "section-1 section-2 section-3 section-3";
    grid-template-columns: 1fr 1fr 1fr 1fr;
    @media screen and (max-width: 768px) {
      display: grid;
      grid-template-areas: "header header"
      "section-1 section-2"
      "section-3 section-3";
      gap: 2rem;
      grid-template-columns: 1fr 1fr;
    }
    // gap: 10vw;
  }
  .footer-header{
    border-block: 1px solid #ffffff1f;
    padding-block: 10px;
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 5fr;

    // display: flex;
    // justify-content: start;
    gap: 10vw;
    grid-area: header;
    margin-block: 10px;

    @media screen and (max-width: 768px) {
      grid-template-columns: 2fr 2fr 1fr;
    }
  }
  .footer-section-1{
    grid-area: section-1;
  }
  .footer-section-2{
    grid-area: section-2;
  }
  .footer-section-3{
    grid-area: section-3;
  }
  .image-container {
    width: 400px;
    height: 200px;
    background-image: url('https://www.newsshooter.com/wp-content/uploads/2016/10/DSC05740-1-1.jpg');
    background-size: cover;
    background-position: center;
    position: relative;

    img {
      width: 100%;
      height: auto;
      object-fit: cover;
    }
  }

  .image-container:after {
    content: 'Play Now';
    width: 100px;
    height: 40px;
    position: absolute;
    background-color: rgba(255, 255, 255, 0.819);
    text-align: center;
    display: grid;
    align-items: center;
    border-radius: 5px;

    color: black;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .card-border-gradient {
    border-radius: 5px;
    padding: 20px 20px;
    position: relative;
    margin-right: 20px;

    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      border-radius: 20px;
      padding: 1px;
      background: linear-gradient(to right, #332933, #5A5959);
      -webkit-mask:
        linear-gradient(#fff 0 0) content-box,
        linear-gradient(#fff 0 0);
      -webkit-mask-composite: destination-out;
      mask-composite: exclude;

    }
  }
}
</style>

