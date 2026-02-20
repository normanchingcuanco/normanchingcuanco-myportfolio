<template>
  <section id="contact" class="py-5">
    <div class="container">
      <h2 class="text-center mb-4">Contact Me</h2>

      <div class="row g-4 justify-content-center">

        <!-- ================= FORM ================= -->
        <div class="col-12 col-md-6">

          <form @submit.prevent="submitForm" class="premium-contact-form">

            <input
              type="text"
              class="form-control mb-3 premium-input"
              placeholder="Your Name"
              v-model="name"
              required
            />

            <input
              type="email"
              class="form-control mb-3 premium-input"
              placeholder="Your Email"
              v-model="email"
              required
            />

            <textarea
              class="form-control mb-3 premium-input"
              rows="4"
              placeholder="Your Message"
              v-model="message"
              required
            ></textarea>

            <!-- reCAPTCHA -->
            <div ref="recaptchaContainer" class="mb-3"></div>

            <button
              type="submit"
              class="btn btn-contact-primary w-100"
              :disabled="isLoading"
            >
              {{ isLoading ? "Sending..." : "Send Message" }}
            </button>

          </form>

          <p v-if="success" class="text-success mt-3">
            Message sent successfully!
          </p>

          <p v-if="error" class="text-danger mt-3">
            {{ errorMessage }}
          </p>

        </div>

        <!-- ================= MAP ================= -->
        <div class="col-12 col-md-6">
          <div class="ratio ratio-16x9">
            <iframe
              src="https://www.google.com/maps?q=Marikina%20City%20Philippines&output=embed"
              loading="lazy"
              title="Marikina City Map">
            </iframe>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue"

const WEB3FORMS_ACCESS_KEY = "1f421d90-c560-4cb9-a267-4555733e8b5a"
const SITE_KEY = "6LeWu3EsAAAAAFTDcc-aGPIfRjMPP8VgWAKgQ4-H"

const name = ref("")
const email = ref("")
const message = ref("")
const isLoading = ref(false)
const success = ref(false)
const error = ref(false)
const errorMessage = ref("")

const recaptchaContainer = ref(null)
const recaptchaWidgetId = ref(null)
const recaptchaToken = ref("")

function onRecaptchaSuccess(token) {
  recaptchaToken.value = token
}

function onRecaptchaExpired() {
  recaptchaToken.value = ""
}

function renderRecaptcha() {
  if (!window.grecaptcha) return

  recaptchaWidgetId.value = window.grecaptcha.render(
    recaptchaContainer.value,
    {
      sitekey: SITE_KEY,
      callback: onRecaptchaSuccess,
      "expired-callback": onRecaptchaExpired,
    }
  )
}

function resetRecaptcha() {
  if (recaptchaWidgetId.value !== null) {
    window.grecaptcha.reset(recaptchaWidgetId.value)
    recaptchaToken.value = ""
  }
}

onMounted(() => {
  const interval = setInterval(() => {
    if (window.grecaptcha && window.grecaptcha.render) {
      renderRecaptcha()
      clearInterval(interval)
    }
  }, 100)
})

async function submitForm() {
  success.value = false
  error.value = false
  errorMessage.value = ""

  if (!recaptchaToken.value) {
    error.value = true
    errorMessage.value = "Please verify that you are not a robot."
    return
  }

  isLoading.value = true

  try {
    const response = await fetch("https://api.web3forms.com/submit", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
      body: JSON.stringify({
        access_key: WEB3FORMS_ACCESS_KEY,
        subject: "New message from Portfolio",
        name: name.value,
        email: email.value,
        message: message.value,
      }),
    })

    const result = await response.json()

    if (result.success) {
      success.value = true
      name.value = ""
      email.value = ""
      message.value = ""
      resetRecaptcha()
    } else {
      error.value = true
      errorMessage.value = result.message || "Submission failed."
    }

  } catch (err) {
    error.value = true
    errorMessage.value = "Network error. Please try again."
  }

  isLoading.value = false
}
</script>