<template>
  <div>
    <OtherHeader />
      <nuxt />
    <Footer />
  </div>
</template>

<style>
</style>
<script>
  import OtherHeader from "~/components/OtherHeader";
  import Footer from "~/components/Footer";
  export default {
    components: {
      OtherHeader,
      Footer
    },
    head(){
      return {
        title: "Standalone Solution | Digital Services"
      }
    },
    mounted () {
      this.$nextTick(() => {
        this.$nuxt.$loading.start()
        setTimeout(() => this.$nuxt.$loading.finish(), 500)
      })
    }

  }
</script>
