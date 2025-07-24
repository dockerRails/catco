<template>
  <v-footer class="footer-section">
    <v-container>
      <v-row>
        <!-- Company Information -->
        <v-col cols="12" md="4" class="mb-6">
          <div class="d-flex align-center mb-4">
            <v-img
              src="/src/assets/logo.svg"
              alt="Cat Studio Logo"
              max-width="40"
              height="40"
              class="mr-3"
            ></v-img>
            <h3 class="text-h5 font-weight-bold">Cat Studio</h3>
          </div>
          <p class="text-body-2 text-grey-lighten-1 mb-4">
            Professional web design company dedicated to creating unique digital experiences
            for our clients. We believe excellent design can change the world.
          </p>
          <div class="d-flex">
            <v-btn
              v-for="social in socialLinks"
              :key="social.name"
              :href="social.url"
              icon
              variant="text"
              color="primary"
              class="mr-2"
              size="small"
            >
              <v-icon>{{ social.icon }}</v-icon>
            </v-btn>
          </div>
        </v-col>

        <!-- Quick Links -->
        <v-col cols="12" md="2" class="mb-6">
          <h4 class="text-h6 font-weight-bold mb-4">Services</h4>
          <v-list class="bg-transparent">
            <v-list-item
              v-for="service in services"
              :key="service"
              class="pa-0 mb-2"
              min-height="auto"
            >
              <v-list-item-title class="text-body-2 text-grey-lighten-1">
                {{ service }}
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-col>

        <!-- Company Links -->
        <v-col cols="12" md="2" class="mb-6">
          <h4 class="text-h6 font-weight-bold mb-4">Company</h4>
          <v-list class="bg-transparent">
            <v-list-item
              v-for="link in companyLinks"
              :key="link"
              class="pa-0 mb-2"
              min-height="auto"
            >
              <v-list-item-title class="text-body-2 text-grey-lighten-1">
                {{ link }}
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-col>

        <!-- Contact Information -->
        <v-col cols="12" md="4" class="mb-6">
          <h4 class="text-h6 font-weight-bold mb-4">Contact Us</h4>
          <div class="contact-info">
            <div class="d-flex align-center mb-3">
              <v-icon color="primary" class="mr-3">mdi-map-marker</v-icon>
              <span class="text-body-2 text-grey-lighten-1">
                Lujiazui Financial Center, Pudong, Shanghai, China
              </span>
            </div>
            <div class="d-flex align-center mb-3">
              <v-icon color="primary" class="mr-3">mdi-phone</v-icon>
              <span class="text-body-2 text-grey-lighten-1">
                +86 138 0000 0000
              </span>
            </div>
            <div class="d-flex align-center mb-3">
              <v-icon color="primary" class="mr-3">mdi-email</v-icon>
              <span class="text-body-2 text-grey-lighten-1">
                hello@catstudio.com
              </span>
            </div>
            <div class="d-flex align-center">
              <v-icon color="primary" class="mr-3">mdi-clock</v-icon>
              <span class="text-body-2 text-grey-lighten-1">
                Monday - Friday 9:00 AM - 6:00 PM
              </span>
            </div>
          </div>
        </v-col>
      </v-row>

      <!-- Divider -->
      <v-divider class="my-6"></v-divider>

      <!-- Copyright Information -->
      <v-row>
        <v-col cols="12" md="6">
          <p class="text-body-2 text-grey-lighten-2 mb-0">
            © {{ currentYear }} Cat Studio. All rights reserved.
          </p>
        </v-col>
        <v-col cols="12" md="6" class="text-md-right">
          <p class="text-body-2 text-grey-lighten-2 mb-0">
            <router-link
              to="/privacy-policy"
              class="footer-link mr-4"
            >
              Privacy Policy
            </router-link>
            <span class="footer-link mr-4">Terms of Service</span>
            <span class="footer-link">Site Map</span>
          </p>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script setup>
import { computed } from 'vue'

// Current year
const currentYear = computed(() => new Date().getFullYear())

// Social media links
const socialLinks = [
  { name: 'WeChat', icon: 'mdi-wechat', url: '#' },
  { name: 'Weibo', icon: 'mdi-sina-weibo', url: '#' },
  { name: 'GitHub', icon: 'mdi-github', url: '#' },
  { name: 'Dribbble', icon: 'mdi-dribbble', url: '#' }
]

// Services list
const services = [
  'Web Design',
  'Frontend Development',
  'User Experience',
  'Brand Design',
  'Mobile Apps'
]

// Company links
const companyLinks = [
  'About Us',
  'Our Team',
  'News & Updates',
  'Careers',
  'Contact Us'
]
</script>

<style scoped>
.footer-section {
  background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
  color: white;
  padding: 3rem 0 1rem 0;
}

.contact-info {
  line-height: 1.6;
}

.footer-link {
  color: inherit;
  text-decoration: none;
  transition: color 0.3s ease;
  cursor: pointer;
}

.footer-link:hover {
  color: #667eea;
  text-decoration: underline;
}

@media (max-width: 960px) {
  .text-md-right {
    text-align: left !important;
  }
}
</style>
