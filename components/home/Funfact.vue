<template>
    <div>
      <section class="commonSection funfact">
        <div class="container">
          <div class="row">
            <div class="col-lg-3 col-sm-6 col-md-3 noPadding BR">
              <div class="singlefunfact text-center">
                <h1 data-counter="179" class="timer"><span class="countSpan"></span>179</h1>
                <h3>Projects Completed</h3>
              </div>
            </div>
            <div class="col-lg-3 col-sm-6 col-md-3 noPadding BR">
              <div class="singlefunfact text-center">
                <h1 data-counter="48" class="timer"><span class="countSpan"></span>48</h1>
                <h3>Active Clients</h3>
              </div>
            </div>
            <div class="col-lg-3 col-sm-6 col-md-3 noPadding BR">
              <div class="singlefunfact text-center">
                <h1 data-counter="17" class="timer"><span class="countSpan"></span>14</h1>
                <h3>Upcoming Projects</h3>
              </div>
            </div>
            <div class="col-lg-3 col-sm-6 col-md-3 noPadding">
              <div class="singlefunfact text-center">
                <h1 data-counter="33" class="timer"><span class="countSpan">9</span>33</h1>
                <h3>Pipeline</h3>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- <section class="commonSection trustClient">
        <div class="container">
          <div class="row">
            <div class="col-lg-12 col-sm-12">
              <div class="CL_content">
                <img src="/images/home_1/4.jpg" alt="">
                <div class="abc_inner">
                  <div class="row">
                    <div class="col-lg-5 col-sm-5 col-md-5">
                    </div>
                    <div class="col-lg-7 col-sm-7 col-md-7">
                      <div class="abci_content">
                        <h2>We are trusted by more than 8900 clients</h2>
                        <p>
                          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incidi-dunt ut labore et dolore magna aliqua.
                          Ut enim ad minim veniam, quis nostrud exercita-tion ullamco laboris nisi ut aliquip ex ea commodo.
                        </p>
                        <a class="common_btn red_bg" href="#"><span>Learn More</span></a>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section> -->
    </div>
</template>

<script>
    export default {
      name: "Funfact",
      mounted() {
        var skl = true;
        $('.singlefunfact').appear();
        $('.singlefunfact').on('appear', function () {
          if (skl)
          {
            $('.timer').each(function () {
              var $this = $(this);
              jQuery({Counter: 0}).animate({Counter: $this.attr('data-counter')}, {
                duration: 3000,
                easing: 'swing',
                step: function () {
                  var num = Math.ceil(this.Counter).toString();
                  if (Number(num) > 999) {
                    while (/(\d+)(\d{3})/.test(num)) {
                      num = num.replace(/(\d+)(\d{3})/, '<span class="countSpan">' + '$1' + '</span>' + '$2');
                    }
                  }
                  $this.html(num);
                }
              });
            });
            skl = false;
          }
        });
      }
    }
</script>

<style scoped>

</style>
