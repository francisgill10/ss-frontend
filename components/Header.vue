<template>
  <div>
    <header class="header_01" id="header">
      <div class="container-fluid">
        <div class="row">
          <div class="col-lg-8 col-sm-3 col-md-3">
            <div class="navigator">
              <a href="/">Standalone Solution</a>
            </div>
          </div>
          <div class="col-lg-4 col-sm-9 col-md-9">
            <div class="navigator text-right">
              <!-- <a href="#">Whatsapp: +923108559858</a> -->
              <a href="#"><i class="fa fa-phone"></i> 0581585091</a>
              <!-- <a href="#">Email: contact@standalonesolution.com</a> -->
            </div>
          </div>
        </div>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "Header",
  mounted() {
    // Serach popup
    if ($(".searchToggler").length > 0) {
      var todg = true;
      $(".searchToggler").on("click", function (e) {
        e.preventDefault();
        if (todg) {
          $(".searchFixed").fadeIn("slow");
          todg = false;
        } else {
          $(".searchFixed").fadeOut("slow");
          todg = true;
        }
      });

      $(document).mouseup(function (e) {
        var container = $(".searchForms");

        if (!container.is(e.target) && container.has(e.target).length === 0) {
          $(".searchFixed").fadeOut("slow");
          todg = true;
        }
      });
      $("#sfCloser").on("click", function (e) {
        e.preventDefault();
        $(".searchFixed").fadeOut("slow");
        todg = true;
      });
    }
    $(function () {
      $(".singleShopWrap").themeWar();
    });

    //Menu PopUp
    $(document).ready(function () {
      $("#close-popup").on("click", function (e) {
        e.preventDefault();
        $("body").removeClass("menu__open show-overlay-nav");
      });
      $(".hamburger").on("click", function () {
        $(this).toggleClass("is_active"), $("body").toggleClass("menu__open");
      }),
        $(document).keyup(function (e) {
          27 === e.keyCode && $(".menu__open .hamburger").click();
        }),
        $("#open-overlay-nav").on("click", function () {
          $("body").toggleClass("show-overlay-nav");
        }),
        $(".dl-menu__wrap").dlmenu({
          animationClasses: {
            classin: "dl-animate-in-3",
            classout: "dl-animate-out-3",
          },
        });
    });

    //Fixed Header
    $(window).on("scroll", function () {
      if ($(window).scrollTop() > 40) {
        $("#header").addClass("fixedHeader animated flipInX");
      } else {
        $("#header").removeClass("fixedHeader animated flipInX");
      }
      scroll_topmenu();
    });

    //Mobile Menu
    if ($(".mobilemenu").length > 0) {
      $(".mobilemenu").on("click", function () {
        var w = $(window).width();
        $(this).toggleClass("active");
        $(".mainmenu > ul").slideToggle("slow");
      });
      if ($(window).width() < 768) {
        $(".mainmenu > ul li.menu-item-has-children > a").on(
          "click",
          function (e) {
            e.preventDefault();
            $(this).parent().toggleClass("active");
            $(this).parent().children(".sub-menu").slideToggle("slow");
          }
        );
      }
    }

    //Active Menu Scroll
    $(".mainmenu ul li.scroll > a").on("click", function () {
      $("html, body").animate(
        { scrollTop: $(this.hash).offset().top - 68 },
        1000,
        "easeOutCubic"
      );
      return false;
    });

    $(".dl-menu__wrap ul li.scroll > a").on("click", function () {
      if (!$(this).parent().hasClass("menu-item-has-children")) {
        $("html, body").animate(
          { scrollTop: $(this.hash).offset().top - 68 },
          1000,
          "easeOutCubic",
          function () {
            $("body").removeClass("menu__open show-overlay-nav");
          }
        );
        return false;
      } else {
        $("html, body").animate(
          { scrollTop: $(this.hash).offset().top - 68 },
          1000,
          "easeOutCubic"
        );
      }
    });
    function scroll_topmenu() {
      var contentTop = [];
      var contentBottom = [];
      var winTop = $(window).scrollTop();
      var rangeTop = 200;
      var rangeBottom = 500;

      $(".mainmenu")
        .find(".scroll > a")
        .each(function () {
          var atr = $(this).attr("href");
          if ($(atr).length > 0) {
            contentTop.push($($(this).attr("href")).offset().top);
            contentBottom.push(
              $($(this).attr("href")).offset().top +
                $($(this).attr("href")).height()
            );
          }
        });

      $.each(contentTop, function (i) {
        if (winTop > contentTop[i] - rangeTop) {
          $(".mainmenu li.scroll")
            .removeClass("active")
            .eq(i)
            .addClass("active");
        }
      });
    }
  },
};
</script>

<style scoped>
</style>
