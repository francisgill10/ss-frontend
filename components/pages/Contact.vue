<template>
  <section class="commonSection ContactPage">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <!-- <h4 class="sub_title">Contact with us</h4> -->
          <h2 class="sec_title">write us a message</h2>
          <p class="sec_desc">
            We are committed to providing our customers with exceptional service
            while<br />
            offering our employees the best training.
          </p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-8 col-lg-offset-2 col-sm-12 col-md-10">
          <div class="row">
            <div class="col-lg-12 col-sm-12">
              <input
                class="input-form required"
                type="text"
                name="f_name"
                id="f_name"
                v-model="first_name"
                placeholder="First Name"
              />
            </div>
            <div class="col-lg-12 col-sm-12">
              <input
                class="input-form required"
                type="text"
                name="l_name"
                id="l_name"
                v-model="last_name"
                placeholder="Last Name"
              />
            </div>
            <div class="col-lg-12 col-sm-12">
              <input
                class="input-form required"
                type="email"
                name="email"
                id="email"
                v-model="email"
                placeholder="Email Address"
              />
            </div>
            <div class="col-lg-12 col-sm-12">
              <input
                class="input-form"
                type="text"
                name="phone"
                id="phone"
                v-model="phone_number"
                placeholder="Phone Number"
              />
            </div>
            <div class="col-lg-12 col-sm-12">
              <textarea
                class="input-form required"
                name="con_message"
                id="con_message"
                v-model="message"
                placeholder="Write Message"
              ></textarea>
            </div>
          </div>
          <div class="col-lg-12 col-sm-12">
            <h4 class="text-primary" v-if="response">{{ response }}</h4>
            <h4 class="text-danger" v-for="(err, i) in errors" :key="i">{{++i}}. {{ err }}</h4>          
          </div>
          <button
            class="common_btn red_bg"
            @click="save"
            type="submit"
            id="con_submit"
          >
            <span>Send Message</span>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Contact",
  data: () => ({
    response: "",
    errors: [],

    first_name: "",
    last_name: "",
    email: "",
    phone_number: "",
    message: "",
  }),
  methods: {
    save() {
      this.$axios
        .post("lead", {
          first_name: this.first_name,
          last_name: this.last_name,
          email: this.email,
          phone_number: this.phone_number,
          message: this.message,
        })
        .then(({ data }) => {
          if (data.status) {
            this.errors = [];
            this.response = data.message;
          } else {
            this.errors = data.errors;
          }
          setTimeout(() => (this.response = ""), 3000);
        });
    },
  },
};
</script>