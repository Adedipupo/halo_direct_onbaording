<template>
  <main class="main-content main-content-signup">
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
          <h2 class="earn">
            <span style="font-weight:bold">Earn</span> the best commissons.<br />
            Manage the <span style="font-weight:bold">best portfolio</span>
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
            v-show="step === 2 || step === 3 || step === 4 || step === 5"
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
              alt="Halo Invest"
              height="60"
              width="100"
            />
          </NuxtLink>
        </div>
        <div v-show="step === 1" class="account-user">
          <p class="text-center mb-1">
            Create your halo Account
          </p>
          <div class="text-center getStarted">
            <h6>
              Get started on your path to making the most.<br />
              of your money.
            </h6>
          </div>
          <div class="formGroup flex-grow-1 pl-0 pr-0">
            <form
              @submit.prevent=""
              novalidate
              class="d-flex-column align-items-center mx-auto"
            >
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
              <div>
                <ul
                  class="entry-content mt-3 pl-3"
                  style="list-style-type: circle;"
                >
                  <li>
                    <h6>Minimum of 8 characters</h6>
                  </li>
                  <li>
                    <h6>One UPPERCASE character</h6>
                  </li>
                  <li>
                    <h6>One unique character (e.g: !@#$%^&*?)</h6>
                  </li>
                </ul>
              </div>
              <footer>
                <p>
                  <button
                    @click.prevent="next()"
                    type="submit"
                    class="btn btn-block text-white mt-4 mx-auto create-account-button"
                  >
                    <span>Create your halo Account</span>
                  </button>
                </p>
              </footer>
              <h6 class="text-center pt-3">
                Already have an Account?
                <NuxtLink to="/auth/login">Sign in</NuxtLink>
              </h6>
            </form>
          </div>
        </div>

        <div v-show="step === 2" class="account-user">
          <p class="text-center mb-1">
            Tell us who you are
          </p>
          <div class="text-center getStarted">
            <h6>
              We advise that you use the names available on your valid documents
              and ID cards.
            </h6>
          </div>
          <div class="formGroup flex-grow-1 pl-0 pr-0">
            <form
              @submit.prevent=""
              novalidate
              class="d-flex-column align-items-center mx-auto"
            >
              <FormInputGroup
                type="text"
                attribute="First Name"
                v-model="form.firstname"
                placeholder="First Name"
                autocomplete="given-name"
                required
              ></FormInputGroup>
              <FormInputGroup
                type="text"
                attribute="Email"
                v-model="form.lastname"
                placeholder="Last Name"
                autocomplete="given-name"
                required
              ></FormInputGroup>
              <FormInputGroup
                type="date"
                v-model="form.date"
                placeholder="Date of Birth"
                autocomplete="date"
                attribute="Date of Birth"
                required
              ></FormInputGroup>
              <FormInputGroup
                type="text"
                v-model="form.phone"
                placeholder="+234"
                autocomplete="phone"
                attribute="Phone Number"
                required
              ></FormInputGroup>
              <div class="mt-3">
                <h6>I have a referal code</h6>
              </div>
              <div class="row container mt-3">
                <div class="col-md-2"></div>
                <div class="col-md-8">
                  <h6>Upload Verifcation Documents</h6>
                </div>
                <div class="col-md-2">
                  <button
                    @click.prevent="next()"
                    type="submit"
                    class="btn btn-outline-success mx-auto"
                  >
                    Go
                  </button>
                </div>
              </div>
              <h6 class="text-center pt-3">
                By choosing to continue, you agree to our Terms of Service and
                Privacy Policy.
              </h6>
            </form>
          </div>
        </div>
        <div v-show="step === 3" class="account-user">
          <p class="text-center mb-1">
            Which of these do you have?
          </p>
          <div class="text-center getStarted">
            <h6>
              Select a valid document or ID card to Verfiy your identity.
            </h6>
          </div>
          <div class="formGroup flex-grow-1 pl-0 pr-0">
            <form
              @submit.prevent=""
              novalidate
              class="d-flex-column align-items-center mx-auto"
            >
              <div
                class="flex-grow-1 p-5 pl-0 pr-0 container align-items-center justify-content-center id-button-div"
              >
                <div class="mb-3">
                  <button
                    type="button"
                    class="btn btn-outline-secondary id-button"
                  >
                    Driver’s Licence
                  </button>
                </div>
                <div class="mb-3">
                  <button
                    type="button"
                    class="btn btn-outline-secondary id-button"
                  >
                    NIN Slip
                  </button>
                </div>
                <div class="mb-3">
                  <button
                    type="button"
                    class="btn btn-outline-secondary id-button"
                  >
                    Voter’s Card
                  </button>
                </div>
                <div class="mb-4">
                  <button
                    type="button"
                    class="btn btn-outline-secondary id-button"
                  >
                    International Passport
                  </button>
                </div>
                <div class="mt-3 mb-5">
                  <h6>What does Halo do with my information?</h6>
                </div>
                <div class="row container mt-3">
                  <div class="col-md-2"></div>
                  <div class="col-md-7">
                    <h6>Select Verifcation Documents</h6>
                  </div>
                  <div class="col-md-3">
                    <button
                      @click.prevent="next()"
                      type="submit"
                      class="btn btn-outline-success mx-auto"
                    >
                      Next
                    </button>
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
        <div v-show="step === 4" class="account-user">
          <p class="text-center mb-1">
            Upload ID Documents
          </p>
          <div class="text-center getStarted">
            <h6>
              Enter the unique ID number on your card. It is the number
              highlighted in the card shown below.
            </h6>
          </div>
          <div
            class="flex-grow-1 pl-0 pr-0 container align-items-center justify-content-center"
          >
            <form
              @submit.prevent=""
              novalidate
              class="align-items-center mx-auto"
            >
              <div class="p-5 mt-3">
                <div>
                  <img
                    src="~assets/gfx/idcard.png"
                    alt="ID Card"
                    height="150"
                    width="250"
                  />
                </div>
                <div class="mb-4">
                  <button
                    type="button"
                    class="btn btn-outline-secondary id-num"
                  >
                    Enter ID Number
                  </button>
                </div>
                <div class="mt-3 mb-5">
                  <h6>What does Halo do with my information?</h6>
                </div>
                <div class="row container mt-3">
                  <div class="col-md-2"></div>
                  <div class="col-md-8">
                    <h6>Upload a selfie photo</h6>
                  </div>
                  <div class="col-md-2">
                    <button
                      @click.prevent="next()"
                      type="submit"
                      class="btn btn-outline-success mx-auto"
                    >
                      Go
                    </button>
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
        <div v-show="step === 5" class="account-user">
          <p class="text-center mb-1">
            Upload ID Documents
          </p>
          <div class="text-center getStarted">
            <h6>
              Take and upload a front and back photo of your ID card/Document.
              Make sure the photo is well lit and clearly shows your name,
              passport and ID number.
            </h6>
          </div>
          <div class="formGroup flex-grow-1 pl-0 pr-0">
            <form
              @submit.prevent=""
              novalidate
              class="d-flex-column align-items-center mx-auto"
            >
              <div>
                <b-form-file
                  v-model="file"
                  :state="Boolean(file)"
                  size="sm"
                ></b-form-file>
                <p>{{ file ? file.name : "" }}</p>
              </div>
              <button class="btn btn-outline-secondary">
                <i
                  class="fas fa-cloud-upload-alt fa-lg ml-5 grey-text"
                  aria-hidden="true"
                ></i
                >&nbsp;&nbsp;
                <input
                  class="file-path validate my-3 "
                  type="text"
                  style="border:none;"
                  placeholder="Upload your file ..."
                />
              </button>
              <footer>
                <p>
                  <button
                    @click.prevent="next()"
                    type="submit"
                    class="btn btn-block text-white mt-4 mx-auto create-account-button"
                  >
                    <span>Upload Documents</span>
                  </button>
                </p>
              </footer>
              <div class="row container mt-3">
                <div class="col-md-2"></div>
                <div class="col-md-7">
                  <h6>Select Verifcation Documents</h6>
                </div>
                <div class="col-md-3">
                  <button
                    @click.prevent="next()"
                    type="submit"
                    class="btn btn-outline-success mx-auto"
                  >
                    Go
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
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
        firstname: null,
        lastname: null,
        phone: null,
        date: null
      },
      file: undefined
    };
  },
  methods: {
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
