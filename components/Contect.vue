<template>
  <section class="bg-gray-900 p-10">
    <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md js-show-on-scroll">
      <h2
        class="mb-4 text-4xl tracking-tight font-extrabold text-center text-white"
      >
        Contact Us
      </h2>
      <p class="mb-8 lg:mb-16 font-light text-center text-gray-400 sm:text-xl">
        Share your thoughts with us! We are currently refining our
        groundbreaking medical and wellness tourism app to offer you a seamless,
        transparent, and personalized experience in finding and booking
        healthcare providers in Thailand. If you're intrigued by our concept,
        have suggestions for enhancement, or would like to be among the first
        users of our platform, please don't hesitate to reach out. We'd love to
        hear from you and have you be part of our exciting journey!
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
            placeholder="name@flowbite.com"
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
            placeholder="Let us know how we can help you"
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
    }
  },
  mounted() {
    emailjs.init(process.env.EMAILJS_PUBLICKEY)
  },
  methods: {
    submitForm() {
      console.log(this.email, this.subject, this.message)
      if (this.email && this.subject && this.message) {
        try {
          emailjs.send('service_di89x0v', 'template_y6hkrgq', {
            email: this.email,
            message: this.message,
            Subject: this.subject,
          })
        } catch (err) {
          console.log(err)
        }
        this.email = ''
        this.subject = ''
        this.message = ''
      }
    },
  },
}
</script>
