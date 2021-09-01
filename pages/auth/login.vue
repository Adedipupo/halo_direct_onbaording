<template>
  <main class="main-content main-content-login">
    <div class="row min-vh-100">
      <div
        class="col-lg-6 p-4 align-items-center justify-content-center signin-login-container"
      >
        <p class="mt-5 ml-3 mb-0">
          <NuxtLink to="/">
            <img
              src="~assets/gfx/halo-direct-logo.svg"
              alt="Halo Invest"
              height="60"
              width="240"
            />
          </NuxtLink>
        </p>
        <div class="mt-5 mw-380 mx-auto flex-grow-1 earn-commission">
          <h2 class="earn fw-light">
            <span style="font-weight:bold">Earn</span> the best commissons.<br />
            Manage the <span style="font-weight:bold">best portfolios</span>
          </h2>

          <div class="one">
            <div class="img12">
              <img
                src="~assets/gfx/illustrations/ese.png"
                height="70"
                width="65"
              />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            </div>
            <div class="line">
              <span class="fw-lighter">Fully licensed by the</span
              ><br />Nigerian Securities & Exchange Commission.
            </div>
          </div>

          <div v-show="step === 1" class="centerImg">
            <img class="showImage" src="~assets/gfx/illustrations/fd.png" />
          </div>
          <div
            v-show="
              step === 2
            "
            class="centerImg"
          >
            <img class="showImage" src="~assets/gfx/illustrations/fd2.png" />
          </div>
        </div>
      </div>
      <div
        class="col-lg-6 p-3 container align-items-center justify-content-center"
      >
        <div class="logoShow mt-2 ml-3 mb-n2">
          <NuxtLink to="/">
            <img
              src="~assets/gfx/halo-direct-logo2.svg"
              alt="Halo Direct"
              height="60"
              width="100"
            />
          </NuxtLink>
        </div>
        <form
          @submit.prevent=""
          novalidate
          class="d-flex-column align-items-center mx-auto"
        >
          <div v-show="step === 1" class="account-user">
            <p class="text-center mb-1">
              Welcome back
            </p>
            <div class="text-center getStarted">
              <h6>
               Log-in and get back to making the most of your money.
              </h6>
            </div>
            <div class="formGroup flex-grow-1 pl-0 pr-0">
              <FormInputGroup
                type="text"
                attribute="Email"
                v-model="form.email"
                placeholder="Email Address"
                autocomplete="given-name"
                required
              ></FormInputGroup>
              <FormInputGroupPassword
                type="password"
                v-model="form.password"
                autocomplete="new-password"
                attribute="Password"
                placeholder="Password"
                inputId="password-input"
                required
              ></FormInputGroupPassword>
              <footer>
                <p>
                  <button
                    type="submit"
                    class="btn btn-block text-white mt-4 mx-auto create-account-button"
                  >
                    <span>Sign in</span>
                  </button>
                </p>
              </footer>
              <h6 class="text-center pt-3">
                <a href @click.prevent="next()">Login with phone number instead</a>
              </h6>
              <h6 class="text-center pt-3 fw-lighter">
                I forgot my password
              </h6>
              <h6 class="text-center pt-3">
                Don't have an account?
                <NuxtLink to="/auth/signup">Learn how you can sign up</NuxtLink>
              </h6>
            </div>
          </div>
          <div v-show="step === 2" class="account-user">
            <p class="text-center mb-1">
              Welcome back
            </p>
            <div class="text-center getStarted">
              <h6>
               Log-in and get back to making the most of your money.
              </h6>
            </div>
            <div class="formGroup flex-grow-1 pl-0 pr-0">
              <FormInputGroup
                type="text"
                v-model="form.phone"
                placeholder="+234"
                autocomplete="phone"
                attribute="Phone Number"
                required
              ></FormInputGroup>
              <FormInputGroupPassword
                type="password"
                v-model="form.password"
                autocomplete="new-password"
                attribute="Password"
                placeholder="Password"
                inputId="password-input"
                required
              ></FormInputGroupPassword>
              <footer>
                <p>
                  <button
                    type="submit"
                    class="btn btn-block text-white mt-4 mx-auto create-account-button"
                  >
                    <span>Sign in</span>
                  </button>
                </p>
              </footer>
              <h6 class="text-center pt-3">
                <a href @click.prevent="prev()">Login with email number instead</a>
              </h6>
              <h6 class="text-center pt-3 fw-lighter">
                I forgot my password
              </h6>
              <h6 class="text-center pt-3">
                Don't have an account?
                <NuxtLink to="/auth/login">Learn how you can sign up</NuxtLink>
              </h6>
            </div>
          </div>

        </form>
        <div class="about">
          <div class="row aboutRow p-3 mt-3">
            <div class="col-lg-8">
              <h6 class="fw-lighter">
                ©2019 Halo Direct is a financial service powered and provided by
                Halo Capital Management Limited ("Halo"). Halo is an asset
                management firm licensed and regulated by the Securities and
                Exchange Commission (SEC).
              </h6>
            </div>
            <div class="col-lg-4">
              <h6>Halo DirectAll rights reserved (c) 2021</h6>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      step: 1,
      form: {
        email: null,
        phone: null,
        date: null
      },
    };
  },
  methods: {
    prev() {
      this.step--;
    },
    next() {
      this.step++;
    },
    submit() {
      alert("Submit to blah and show blah and etc.");
    }
  }
};
</script>

<style scoped>
.signin-login-container {
  background-color: #10286a;
  color: #ffff;
}
.img1 {
  margin: 3rem;
}
.earn {
  margin-left: 5rem;
}
.earn-commission {
  font-family: "Gilroy";
}
.one {
  display: flex;
  margin-top: 3rem;
  margin-left: 4rem;
}
.showImage {
  text-align: center;
  height: 57vh;
  width: 90%;
  margin-bottom: -2rem;
}
.account-user {
  font-family: "Gilory";
  font-size: 25px;
  font-weight: bold;
  margin-top: 4rem;
}
form {
  width: 50%;
}
.getStarted {
  font-family: "Nunito";
  margin-top: 1rem;
}
.entry-content {
  font-size: 12px;
}
.create-account-button {
  background: #143285;
  font-family: "Gilroy";
  height: 50px;
}
.about {
  font-family: "Nunito";
  margin-top: 9rem;
}
.id-button-div {
  width: 100%;
}
.id-button {
  text-align: left;
  width: 90%;
  height: 45px;
}
.id-num {
  text-align: left;
  width: 85%;
  height: 40px;
}
@media (min-width: 700px) {
  .logoShow {
    display: none;
  }
}
@media (max-width: 600px) {
  .signin-login-container {
    display: none;
  }
  p {
    font-family: "Nunito";
    font-size: 1rem;
  }
  h6 {
    font-size: 1rem;
  }
  form {
    width: 90%;
  }
  .about {
    font-family: "Nunito";
    margin-top: 6rem;
  }
  .id-button-div {
    width: 100%;
  }
  .id-button {
    text-align: left;
    width: 100%;
    height: 45px;
  }
  .id-num {
    text-align: left;
    width: 90%;
    height: 40px;
  }
}
</style>
