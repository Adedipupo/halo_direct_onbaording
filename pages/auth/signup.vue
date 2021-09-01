<template>
  <main class="main-content main-content-signup">
    <article class="article bg-white">
      <h1 class="sr-only">{{ title }}</h1>

      <div class="row min-vh-100">
        <div
          class="col-lg-6 p-5 d-flex align-items-center justify-content-center bg-white signin-login-container"
        >
          <div class="article-user pl-0 pr-0 mw-380 mx-auto flex-grow-1">
            <h2>Make the most of your money</h2>
            <p>
              Simple, secure savings and investments in the palm of your hands.
            </p>
            <p>
              <img
                src="~assets/gfx/illustrations/goal-sm.svg"
                height="55"
                width="55"
              />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <img
                src="~assets/gfx/illustrations/susu-sm.svg"
                height="55"
                width="55"
              />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <img
                src="~assets/gfx/illustrations/league-sm.svg"
                height="55"
                width="55"
              />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <img
                src="~assets/gfx/illustrations/fixed-sm.svg"
                height="55"
                width="55"
              />
            </p>
          </div>
        </div>

        <div
          class="col-lg-6 p-5 d-flex align-items-center justify-content-center bg-goal"
        >
          <div class="article-user flex-grow-1 pl-0 pr-0">
            <form @submit.prevent="" novalidate class="mw-380 mx-auto">
              <p class="text-center pb-5 mb-3">
                <NuxtLink to="/">
                  <img
                    src="~assets/gfx/halo-invest-logo.svg"
                    alt="Halo Invest"
                    height="60"
                    width="240"
                  />
                </NuxtLink>
              </p>
              <div class="article-user__body">
                <FormInputGroup
                  type="text"
                  attribute="First Name"
                  label="First Name"
                  placeholder="First Name"
                  autocomplete="given-name"
                  required
                ></FormInputGroup>
                <FormInputGroup
                  type="text"
                  attribute="Last Name"
                  label="Last Name"
                  placeholder="Last Name"
                  autocomplete="given-name"
                  required
                ></FormInputGroup>
                <FormInputGroup
                  type="email"
                  label="Email"
                  attribute="Email Address"
                  placeholder="Email Address"
                  autocomplete="email"
                  required
                ></FormInputGroup>
                <FormInputGroup
                  type="text"
                  label="Phone Number"
                  :mask="'0###-###-####'"
                  placeholder="0xxx-xxx-xxxx"
                  autocomplete="phone"
                  attribute="Phone Number"
                  required
                ></FormInputGroup>
                <div>
                  <label> Date of Birth</label>
                  <div class="row">
                    <div class="col-md-4">
                      <FormSelectGroup
                        type="number"
                        label="Day"
                        attribute="birth day"
                        :options="daysList"
                        autocomplete="birth_day"
                        required
                      ></FormSelectGroup>
                    </div>
                    <div class="col-md-4">
                      <FormSelectGroup
                        attribute="month"
                        type="number"
                        label="Month"
                        :options="monthsList"
                        autocomplete="birth-month"
                        required
                      ></FormSelectGroup>
                    </div>
                    <div class="col-md-4">
                      <FormSelectGroup
                        attribute="year"
                        type="number"
                        label="Year"
                        :options="yearsList"
                        autocomplete="bday-year"
                        required
                      ></FormSelectGroup>
                    </div>
                  </div>
                </div>
                <FormInputGroupPassword
                  type="password"
                  label="Password"
                  autocomplete="new-password"
                  attribute="Password"
                  placeholder="password"
                  inputId="password-input"
                  required
                ></FormInputGroupPassword>
              </div>

              <div class="col-md-12 mt-3 mb-4 pad-0">
                <FormInputGroup
                  type="referral"
                  label=""
                  attribute="Referral"
                  placeholder="Enter your referral code"
                ></FormInputGroup>
              </div>

              <footer class="article-footer pt-3 text-center">
                <label for="agreements"
                  ><input
                    type="checkbox"
                    name="agreements"
                    v-model="isNotAgreed"
                  />
                  &nbsp;I have read and agree to the
                  <a
                    href="/terms-and-conditions"
                    style="text-decoration:underline"
                    target="_blank"
                    >terms of usage</a
                  >
                  and the
                  <a
                    href="/privacy-policy"
                    style="text-decoration:underline"
                    target="_blank"
                    >investment terms</a
                  ></label
                >

                <p>
                  <button
                    type="submit"
                    class="btn btn-primary btn-block text-white mt-3"
                    @click="submit(1)"
                    :disabled="isSignUpLoading || !isNotAgreed"
                  >
                    Sign up
                  </button>
                </p>
              </footer>

              <footer>
                <div class="pt-2 text-center">
                  <p class="mb-3">
                    <NuxtLink to="/login/" class="invest-link"
                      >Already have an account? Log in</NuxtLink
                    >
                  </p>
                  <p>
                    <NuxtLink to="/legal" class="invest-link" target="_blank"
                      >Click Here</NuxtLink
                    >
                    to Read The Terms and Agreements
                  </p>
                </div>
              </footer>
            </form>
          </div>
          <Loading message="We are about to send you a confirmation email" />
        </div>
      </div>
    </article>
  </main>
</template>

<script>
export default {};
</script>
