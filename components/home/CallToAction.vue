<template>
  <section class="cta commonSection" :class="[design === 'style2' ? 'ready_2' : 'ready']">
    <div class="container">
      <div class="row">
        <div class="col-lg-9 col-sm-8 col-md-9">
          <h2 class="sec_title white">Let's Get Your Project Started!</h2>
        </div>
        <div class="col-lg-3 col-sm-4 col-md-3 text-right">
          <a class="common_btn" target="_blank" :class="[design === 'style2' ? 'red_bg' : '']" href="https://api.whatsapp.com/send/?phone=923108559858&text&app_absent=0"><span>Get Pricing</span></a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
    export default {
      name: "CallToAction",
      props: {
        design: {
          type: String,
          default: 'style1'
        }
      }
    }
</script>

<style scoped>
 .cta {
   margin-top: -10px;
 }
</style>
