<template>
  <div id="home-page" class="page-wrapper home-page">
    <site-hero :title="title" :subtitle="subtitle" :image="featureImage">
	<div class="social-main">
	<a href="https://www.youtube.com/channel/UCOyYK29kVXQvknRwdW_3-YQ" target="_blank"><i class="fab fa-youtube" data-v-0efc0558="" aria-hidden="true" style="
    padding: 0px 20px 0px 10px;
    font-size: 35px;
"></i></a>
	<a href="https://www.instagram.com/catalystcoder/" target="_blank"><i class="fab fa-instagram" data-v-0efc0558="" aria-hidden="true" style="
    padding: 0px 20px 0px 10px;
    font-size: 35px;
"></i></a>
	<a href="https://twitter.com/catalyst_coder" target="_blank"><i class="fab fa-twitter" data-v-0efc0558="" aria-hidden="true" style="
    padding: 0px 20px 0px 10px;
    font-size: 35px;
"></i></a>
	</div>
      <button
        v-if="$siteConfig.newsletter.on"
        class="button is-primary"
        @click="$eventBus.$emit('modal-triggered', 'newsletter-modal')"
      >
        Subscribe To Newsletter
      </button>
	  
    </site-hero>
    <main-section theme="one-column">
      <template v-slot:default>
        <!-- All Posts -->
        <posts-grid />
      </template>
      <template v-slot:sidebar>
        Nothing here
      </template>
    </main-section>
    <news-letter-form-modal />
  </div>
  <div style="display:none!important">
  <form name="contact" action="post" data-netlify="true" >
  <input type="hidden" name="form-name" value="ask-question" />
    <!-- Name -->
    <div class="field">
      <label class="label is-medium">Name</label>
      <div class="control has-icons-left">
        <input class="input is-medium" type="text" placeholder="John Smith" />
        <span class="icon is-small is-left">
          <font-awesome-icon icon="user" />
        </span>
      </div>
    </div>
    <!-- Email -->
    <div class="field">
      <label class="label is-medium">Email</label>
      <div class="control has-icons-left">
        <input
          class="input is-medium"
          type="email"
          placeholder="you@email.com"
        />
        <span class="icon is-small is-left">
          <font-awesome-icon icon="envelope" />
        </span>
      </div>
    </div>
    <!-- Subject -->
    <div class="field">
      <label class="label is-medium">Subject</label>
      <div class="control has-icons-left">
        <input
          class="input is-medium"
          type="text"
          placeholder="Brief Summary"
        />
        <span class="icon is-small is-left">
          <font-awesome-icon icon="briefcase" />
        </span>
      </div>
    </div>
    <!-- Message -->
    <div class="field">
      <label class="label is-medium">Message</label>
      <div class="control">
        <textarea
          class="textarea"
          placeholder="Detailed description of your comment, request, etc"
          rows="8"
        ></textarea>
      </div>
    </div>
	<div class="field">
	<div data-netlify-recaptcha="true"></div>
    <div class="control">
      <button class="button is-primary" type="submit">
        Contact Us
      </button>
    </div>
  </form>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { setPageData } from '../helper'
import NewsLetterFormModal from '~/components/NewsLetterFormModal'

export default {
  name: 'HomePage',
  head() {
    return {
      title: `Home | ${this.$siteConfig.siteName}`
    }
  },
  components: {
    NewsLetterFormModal
  },
  computed: {
    ...mapState(['title', 'subtitle', 'featureImage'])
  },
  fetch({ store, params }) {
    setPageData(store, { slug: 'home' })
  }
}
</script>

<style>
.home-page .under-subtitle {
  border-top: none;
}
.social-main a i{
font-size:25px;
padding: 0px 20px 10px 10px;

}
</style>
