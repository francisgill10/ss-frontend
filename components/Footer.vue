<template>
  <div>
    <footer class="footer_1">
      <div class="container">
        <div class="row">
          <div class="col-lg-5 col-sm-6 col-md-5">
            <aside class="widget aboutwidget">
              About Us
              <!-- <a href="#"><img src="/images/foo_logo.png" alt=""></a> -->
              <p>
                We are here to provide the best on demand services. No need hire a programmer or developer. 
                No need to give the big amount to the Tech Company. You just need to give us the project as out source in most reasonable cost.
              </p>
              <!-- <b>"We only charge after the project completion."</b> -->
            </aside>
          </div>
          <div class="col-lg-4 col-sm-4 col-md-4">
            <aside class="widget contact_widgets">
              <h3 class="widget_title">contact</h3>
              <p>Deira Dubai near fish round about, UAE</p>
              <p>P: +971581585091</p>
              <p>WA: +923108559858</p>
              <p>E: contact@standalonesolution.com</p>
            </aside>
          </div>
          <div class="col-lg-3 col-sm-2 col-md-3">
            <aside class="widget social_widget">
              <h3 class="widget_title">social</h3>
              <ul>
                <li>
                  <a target="_blank" href="https://twitter.com/"
                    ><i class="fa fa-twitter"></i>Twitter</a
                  >
                </li>
                <li>
                  <a target="_blank" href="https://web.facebook.com/"
                    ><i class="fa fa-facebook-square"></i>Facebook</a
                  >
                </li>
                <li>
                  <a target="_blank" href="https://youtube.com/"
                    ><i class="fa fa-youtube-play"></i>Youtube</a
                  >
                </li>
              </ul>
            </aside>
          </div>
        </div>

        <div class="row">
          <div class="col-lg-12 col-sm-12 text-center">
            <div class="copyright">
              © copyright {{ new Date().getFullYear() }} by
              <a href="#">standalonesolutions.com</a>
            </div>
          </div>
        </div>
      </div>
      <a href="https://api.whatsapp.com/send/?phone=923108559858&text&app_absent=0" target="_blank">
        <img style="width:100px;margin-top: -9%;" src="/images/wa-logo.png" alt="" />
      </a>
    </footer>

    <!-- Bact To To -->
    <a id="backToTop" href="#" class=""
      ><i class="fa fa-angle-double-up"></i
    ></a>

    <!-- Bact To To -->
  </div>
</template>

<script>
export default {
  name: "Footer",
  mounted() {
    var back = $("#backToTop"),
      body = $("body, html");
    $(window).on("scroll", function () {
      var h = $(window).height() / 2;
      if ($(window).scrollTop() > h) {
        back.addClass("showit");
      } else {
        back.removeClass("showit");
      }
    });
    body.on("click", "#backToTop", function (e) {
      e.preventDefault();
      body.animate({ scrollTop: 0 }, 800);
    });
  },
};
</script>

<style scoped>
</style>
