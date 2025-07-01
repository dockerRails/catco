<template>
  <div>
    <!-- Hero Section -->
    <v-container fluid class="hero-section pa-0">
      <v-row no-gutters class="fill-height align-center justify-center text-center">
        <v-col cols="12">
          <div class="hero-content">
            <v-img
              src="/src/assets/logo.svg"
              alt="Cat Studio Logo"
              class="mx-auto mb-6"
              max-width="120"
              height="120"
            ></v-img>
            <h1 class="display-1 font-weight-bold mb-4 text-gradient">
              Cat Studio
            </h1>
            <p class="headline mb-6 text-grey-lighten-1">
              Professional Web Design | Creative Excellence | Premium Quality
            </p>
            <p class="title mb-8 text-grey-lighten-2">
              We craft unique digital experiences for your brand, making every pixel shine with excellence
            </p>
            <v-btn
              color="primary"
              size="large"
              rounded="lg"
              class="px-8 py-3 mr-4"
              @click="scrollToSection('services')"
            >
              <v-icon start>mdi-rocket-launch</v-icon>
              Start Project
            </v-btn>
            <v-btn
              variant="outlined"
              color="white"
              size="large"
              rounded="lg"
              class="px-8 py-3"
              @click="scrollToSection('portfolio')"
            >
              <v-icon start>mdi-eye</v-icon>
              View Portfolio
            </v-btn>
          </div>
        </v-col>
      </v-row>
    </v-container>

    <!-- Services Section -->
    <v-container id="services" class="py-16">
      <v-row>
        <v-col cols="12" class="text-center mb-12">
          <h2 class="display-1 font-weight-bold mb-4">Our Services</h2>
          <p class="headline text-grey-lighten-1">
            Professional design team providing comprehensive web solutions
          </p>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="4" v-for="service in services" :key="service.title">
          <v-card
            class="service-card h-100"
            elevation="8"
            rounded="lg"
            hover
          >
            <v-card-text class="pa-8 text-center">
              <v-avatar
                size="80"
                :color="service.color"
                class="mb-6"
              >
                <v-icon size="40" color="white">{{ service.icon }}</v-icon>
              </v-avatar>
              <h3 class="text-h5 font-weight-bold mb-4">{{ service.title }}</h3>
              <p class="text-body-1 text-grey-lighten-1 mb-4">
                {{ service.description }}
              </p>
              <v-chip
                v-for="feature in service.features"
                :key="feature"
                class="ma-1"
                color="primary"
                variant="outlined"
                size="small"
              >
                {{ feature }}
              </v-chip>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Portfolio Section -->
    <v-container id="portfolio" fluid class="portfolio-section py-16">
      <v-container>
        <v-row>
          <v-col cols="12" class="text-center mb-12">
            <h2 class="display-1 font-weight-bold mb-4">Featured Portfolio</h2>
            <p class="headline text-grey-lighten-1">
              Every project is our masterpiece crafted with precision
            </p>
          </v-col>
        </v-row>
        <v-row>
          <v-col
            cols="12"
            md="6"
            lg="4"
            v-for="(project, index) in portfolio"
            :key="index"
          >
            <v-card
              class="portfolio-card"
              elevation="12"
              rounded="lg"
              hover
            >
              <v-img
                :src="project.image"
                height="250"
                cover
                class="portfolio-image"
              >
                <div class="overlay d-flex align-center justify-center">
                  <v-btn
                    icon
                    size="large"
                    color="white"
                    class="overlay-btn"
                  >
                    <v-icon size="30">mdi-eye</v-icon>
                  </v-btn>
                </div>
              </v-img>
              <v-card-text class="pa-6">
                <h4 class="text-h6 font-weight-bold mb-2">{{ project.title }}</h4>
                <p class="text-body-2 text-grey-lighten-1 mb-3">
                  {{ project.description }}
                </p>
                <v-chip
                  v-for="tech in project.technologies"
                  :key="tech"
                  class="ma-1"
                  color="secondary"
                  size="small"
                >
                  {{ tech }}
                </v-chip>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-container>

    <!-- About Section -->
    <v-container id="about" class="py-16">
      <v-row align="center">
        <v-col cols="12" md="6">
          <h2 class="display-1 font-weight-bold mb-6">About Cat Studio</h2>
          <p class="text-h6 mb-4 text-grey-lighten-1">
            We are a creative and passionate design team
          </p>
          <p class="text-body-1 mb-4">
            Cat Studio was founded in the golden age of digital creativity. We specialize in 
            providing high-quality web design services for businesses and individuals. 
            We believe that excellent design is not just a visual feast, but the perfect 
            interpretation of user experience.
          </p>
          <p class="text-body-1 mb-6">
            Our team consists of senior designers, front-end developers, and user experience 
            experts, committed to perfectly combining the latest design trends with practicality, 
            creating unique digital solutions for every client.
          </p>
          <v-row class="mb-6">
            <v-col cols="6" sm="3" v-for="stat in stats" :key="stat.label">
              <div class="text-center">
                <div class="text-h4 font-weight-bold text-primary">{{ stat.value }}</div>
                <div class="text-body-2 text-grey-lighten-1">{{ stat.label }}</div>
              </div>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="12" md="6">
          <v-card elevation="8" rounded="lg" class="pa-8">
            <h3 class="text-h5 font-weight-bold mb-4">Our Advantages</h3>
            <v-list class="bg-transparent">
              <v-list-item
                v-for="advantage in advantages"
                :key="advantage.title"
                class="pa-3"
              >
                <template v-slot:prepend>
                  <v-avatar size="40" :color="advantage.color">
                    <v-icon color="white">{{ advantage.icon }}</v-icon>
                  </v-avatar>
                </template>
                <v-list-item-title class="font-weight-bold mb-1">
                  {{ advantage.title }}
                </v-list-item-title>
                <v-list-item-subtitle>
                  {{ advantage.description }}
                </v-list-item-subtitle>
              </v-list-item>
            </v-list>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Contact Section -->
    <v-container id="contact" fluid class="contact-section py-16">
      <v-container>
        <v-row>
          <v-col cols="12" class="text-center mb-12">
            <h2 class="display-1 font-weight-bold mb-4">Contact Us</h2>
            <p class="headline text-grey-lighten-1">
              Ready to start your project? Let's create magic together
            </p>
          </v-col>
        </v-row>
        <v-row justify="center">
          <v-col cols="12" md="8" lg="6">
            <v-card elevation="12" rounded="lg" class="pa-8">
              <v-form ref="form" v-model="valid">
                <v-row>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      v-model="contactForm.name"
                      label="Full Name"
                      variant="outlined"
                      :rules="nameRules"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      v-model="contactForm.email"
                      label="Email Address"
                      variant="outlined"
                      :rules="emailRules"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                      v-model="contactForm.subject"
                      label="Project Subject"
                      variant="outlined"
                      :rules="subjectRules"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-textarea
                      v-model="contactForm.message"
                      label="Project Details"
                      variant="outlined"
                      rows="4"
                      :rules="messageRules"
                      required
                    ></v-textarea>
                  </v-col>
                  <v-col cols="12" class="text-center">
                    <v-btn
                      color="primary"
                      size="large"
                      rounded="lg"
                      class="px-8"
                      :disabled="!valid"
                      @click="submitForm"
                    >
                      <v-icon start>mdi-send</v-icon>
                      Send Message
                    </v-btn>
                  </v-col>
                </v-row>
              </v-form>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-container>

    <!-- Footer -->
    <AppFooter />
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import AppFooter from '@/components/AppFooter.vue'

// 响应式数据
const valid = ref(false)

const contactForm = reactive({
  name: '',
  email: '',
  subject: '',
  message: ''
})

// 服务数据
const services = ref([
  {
    title: 'Web Design',
    description: 'From concept to implementation, we create visually stunning websites that perfectly blend aesthetics with functionality.',
    icon: 'mdi-palette',
    color: 'primary',
    features: ['Responsive Design', 'UI/UX Optimization', 'Brand Consistency', 'Visual Design']
  },
  {
    title: 'Frontend Development',
    description: 'Using the latest technology stack to ensure your website is fast, stable, and highly compatible.',
    icon: 'mdi-code-tags',
    color: 'success',
    features: ['Vue.js', 'React', 'Performance Optimization', 'Cross-browser Compatibility']
  },
  {
    title: 'User Experience',
    description: 'Deep research into user behavior to create intuitive and smooth user experiences.',
    icon: 'mdi-account-heart',
    color: 'warning',
    features: ['User Research', 'Interaction Design', 'Usability Testing', 'Experience Optimization']
  }
])

// 作品集数据
const portfolio = ref([
  {
    title: 'Fashion Brand Website',
    description: 'High-end e-commerce website for a renowned fashion brand, boosting sales by 200%',
    image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=500&h=300&fit=crop',
    technologies: ['Vue.js', 'Vuetify', 'Node.js']
  },
  {
    title: 'Tech Company Portal',
    description: 'Modern corporate portal website enhancing brand image and user experience',
    image: 'https://images.unsplash.com/photo-1551650975-87deedd944c3?w=500&h=300&fit=crop',
    technologies: ['React', 'TypeScript', 'GraphQL']
  },
  {
    title: 'Restaurant Chain Platform',
    description: 'Comprehensive restaurant management platform improving operational efficiency by 300%',
    image: 'https://images.unsplash.com/photo-1551650975-87deedd944c3?w=500&h=300&fit=crop',
    technologies: ['Vue.js', 'PWA', 'Firebase']
  }
])

// 统计数据
const stats = ref([
  { value: '100+', label: 'Completed Projects' },
  { value: '50+', label: 'Happy Clients' },
  { value: '3+', label: 'Years Experience' },
  { value: '99%', label: 'Client Satisfaction' }
])

// 优势数据
const advantages = ref([
  {
    title: 'Expert Team',
    description: 'Senior designers and developers',
    icon: 'mdi-account-group',
    color: 'primary'
  },
  {
    title: 'Fast Delivery',
    description: 'Efficient workflow, on-time delivery',
    icon: 'mdi-rocket-launch',
    color: 'success'
  },
  {
    title: 'Ongoing Support',
    description: 'Technical support after project completion',
    icon: 'mdi-headset',
    color: 'info'
  },
  {
    title: 'Innovative Thinking',
    description: 'Following design trends, innovative solutions',
    icon: 'mdi-lightbulb',
    color: 'warning'
  }
])

// 表单验证规则
const nameRules = [
  v => !!v || 'Name is required',
  v => (v && v.length >= 2) || 'Name must be at least 2 characters'
]

const emailRules = [
  v => !!v || 'Email is required',
  v => /.+@.+\..+/.test(v) || 'Please enter a valid email address'
]

const subjectRules = [
  v => !!v || 'Project subject is required'
]

const messageRules = [
  v => !!v || 'Project details are required',
  v => (v && v.length >= 10) || 'Project details must be at least 10 characters'
]

// 方法
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const submitForm = () => {
  // 这里可以添加表单提交逻辑
  console.log('Form submitted:', contactForm)
  // 显示成功消息或者发送请求
  alert('Thank you for your inquiry! We will contact you soon.')
}
</script>

<style scoped>
.hero-section {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  position: relative;
}

.hero-content {
  position: relative;
  z-index: 2;
  padding: 2rem;
}

.text-gradient {
  background: linear-gradient(45deg, #fff 30%, #f0f0f0 90%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.service-card {
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.service-card:hover {
  transform: translateY(-8px);
}

.portfolio-section {
  background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
}

.portfolio-card {
  transition: all 0.3s ease;
  overflow: hidden;
}

.portfolio-card:hover {
  transform: translateY(-8px);
}

.portfolio-image {
  position: relative;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.portfolio-card:hover .overlay {
  opacity: 1;
}

.overlay-btn {
  transform: scale(0.8);
  transition: transform 0.3s ease;
}

.portfolio-card:hover .overlay-btn {
  transform: scale(1);
}

.contact-section {
  background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
}

@media (max-width: 960px) {
  .hero-section {
    min-height: 80vh;
  }
  
  .hero-content {
    padding: 1rem;
  }
}
</style>
