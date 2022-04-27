<template>
  <section class="commonSection porfolio">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h4 class="sub_title">our portfolio</h4>
          <h2 class="sec_title">work showcase</h2>
          <p class="sec_desc">
            We are committed to providing our customers with exceptional service while<br> offering our employees the best training.
          </p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-4 col-sm-6 col-md-4">
          <div class="singlefolio">
            <img src="/images/portfolio/7.jpg" alt=""/>
            <div class="folioHover">
              <a class="cate" href="/">Budget System</a>
              <h4><nuxt-link to="/">For Insurance Company</nuxt-link></h4>
            </div>
          </div>
           <div class="singlefolio">
            <img src="/images/portfolio/6.jpg" alt=""/>
            <div class="folioHover">
              <a class="cate" href="/">Budget System</a>
              <h4><nuxt-link to="/">For Insurance Company</nuxt-link></h4>
            </div>
          </div>
             <div class="singlefolio">
            <img src="/images/portfolio/1.jpg" alt=""/>
            <div class="folioHover">
              <a class="cate" href="/">Budget System</a>
              <h4><nuxt-link to="/">For Insurance Company</nuxt-link></h4>
            </div>
          </div>
        </div>
        <div class="col-lg-4 col-sm-6 col-md-4">
          <div class="singlefolio">
            <img src="/images/portfolio/2.jpg" alt=""/>
            <div class="folioHover">
              <a class="cate" href="#">Rider website</a>
              <h4><nuxt-link to="/portfolio-detail">Funds collection for community</nuxt-link></h4>
            </div>
          </div>
        </div>
        <div class="col-lg-4 col-sm-6 col-md-4">
          <div class="singlefolio">
            <img src="/images/portfolio/3.jpg" alt=""/>
            <div class="folioHover">
              <a class="cate" href="#">Order Dashboard</a>
              <h4><nuxt-link to="/portfolio-detail">Custom Solution</nuxt-link></h4>
            </div>
          </div>
        </div>

        <div class="col-lg-4 col-sm-6 col-md-4">
          <div class="singlefolio">
            <img src="/images/portfolio/4.png" alt=""/>
            <div class="folioHover">
              <a class="cate" href="#">Login Manager</a>
              <h4><nuxt-link to="/portfolio-detail">Credentials Locker</nuxt-link></h4>
            </div>
          </div>
        </div>

        <div class="col-lg-4 col-sm-6 col-md-4">
          <div class="singlefolio">
            <img src="/images/portfolio/5.png" alt=""/>
            <div class="folioHover">
              <a class="cate" href="#">Report Management</a>
              <h4><nuxt-link to="/portfolio-detail">System for complex reporting</nuxt-link></h4>
            </div>
          </div>
        </div>

        <div class="col-lg-4 col-sm-6 col-md-4">
          <div class="singlefolio">
            <img src="/images/portfolio/3.jpg" alt=""/>
            <div class="folioHover">
              <a class="cate" href="#">Sales Management</a>
              <h4><nuxt-link to="/portfolio-detail">Eye catching dashboard</nuxt-link></h4>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script>
    export default {
      name: "Portfolio"
    }
</script>

<style scoped>

.singlefolio img {
    height: 250px !important;
}

</style>
