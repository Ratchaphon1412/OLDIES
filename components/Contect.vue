<template>
  <section id="contact" class="bg-gray-900 p-10">
    <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md js-show-on-scroll">
      <h2
        class="mb-4 md:text-3xl text-xl tracking-tight font-extrabold text-center text-white"
      >
        Contact Us
      </h2>
      <p class="mb-8 lg:mb-16 font-light text-center text-gray-400 sm:text-xl">
        If you are intrigued by our concept, have suggestions for enhancement,
        or would like to be among the first users of our platform, please do not
        hesitate to reach out. We would love to hear from you and have you be
        part of our exciting journey!
      </p>
      <form action="#" class="space-y-8">
        <div>
          <label
            for="email"
            class="block mb-2 text-sm font-medium text-gray-300"
            >Your email</label
          >
          <input
            v-model="email"
            type="email"
            id="email"
            class="shadow-sm text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 bg-gray-700 border-gray-600 placeholder-gray-400 text-white focus:border-primary-500 shadow-sm-light"
            placeholder="your email address"
            required
          />
        </div>
        <div>
          <label
            for="subject"
            class="block mb-2 text-sm font-medium text-gray-300"
            >Subject</label
          >
          <input
            v-model="subject"
            type="text"
            id="subject"
            class="block p-3 w-full text-sm rounded-lg border shadow-sm focus:ring-primary-500 focus:border-primary-500 bg-gray-700 border-gray-600 placeholder-gray-400 text-white focus:ring-primary-500 focus:border-primary-500 shadow-sm-light"
            placeholder="Subject"
            required
          />
        </div>
        <div class="sm:col-span-2">
          <label
            for="message"
            class="block mb-2 text-sm font-medium text-gray-400"
            >Your message</label
          >
          <textarea
            v-model="message"
            id="message"
            rows="6"
            class="block p-2.5 w-full text-sm rounded-lg shadow-sm border focus:ring-primary-500 focus:border-primary-500 bg-gray-700 border-gray-600 placeholder-gray-400 text-white focus:ring-primary-500 focus:border-primary-500"
            placeholder="Leave a comment..."
          ></textarea>
        </div>
        <button
          @click="submitForm"
          type="submit"
          class="py-3 px-5 text-sm font-medium text-center text-white rounded-lg sm:w-fit focus:ring-4 focus:outline-none bg-gray-600 hover:bg-gray-700 focus:ring-primary-800"
        >
          Send message
        </button>
      </form>

      <!--alert done to send mail-->
      <div
        v-show="donealert"
        id="alert-3"
        class="flex p-4 mb-4 mt-4 text-green-800 rounded-lg bg-green-50 dark:bg-gray-800 dark:text-green-400"
        role="alert"
      >
        <svg
          aria-hidden="true"
          class="flex-shrink-0 w-5 h-5"
          fill="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z"
            clip-rule="evenodd"
          ></path>
        </svg>
        <span class="sr-only">Info</span>
        <div class="ml-3 text-sm font-medium">
          Complete the form to send us a message.
        </div>
      </div>
      <!--alert fail to send mail-->
      <div
        v-show="failalert"
        id="alert-2"
        class="flex p-4 mb-4 mt-4 text-red-800 rounded-lg bg-red-50 dark:bg-gray-800 dark:text-red-400"
        role="alert"
      >
        <svg
          aria-hidden="true"
          class="flex-shrink-0 w-5 h-5"
          fill="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z"
            clip-rule="evenodd"
          ></path>
        </svg>
        <span class="sr-only">Info</span>
        <div class="ml-3 text-sm font-medium">Fail to send message.</div>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from 'emailjs-com'
export default {
  name: 'Contact',

  data() {
    return {
      email: '',
      subject: '',
      message: '',
      failalert: false,
      donealert: false,
    }
  },

  mounted() {
    console.log(process.env.EMAILJS_PUBLICKEY)
    emailjs.init(process.env.EMAILJS_PUBLICKEY)
  },
  methods: {
    submitForm() {
      this.failalert = false
      this.donealert = false
      console.log(this.email, this.subject, this.message)
      if (this.email && this.subject && this.message) {
        try {
          emailjs.send('service_di89x0v', 'template_y6hkrgq', {
            email: this.email,
            message: this.message,
            Subject: this.subject,
          })
          this.donealert = true
        } catch (err) {
          console.log(err)
          this.failalert = true
        }
        this.email = ''
        this.subject = ''
        this.message = ''
      }
    },
  },
}
</script>
