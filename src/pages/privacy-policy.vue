<template>
  <div>
    <!-- Header Section -->
    <v-container fluid class="header-section pa-0">
      <v-row no-gutters class="fill-height align-center justify-center text-center">
        <v-col cols="12">
          <div class="header-content">
            <h1 class="display-1 font-weight-bold mb-4 text-gradient">
              Privacy Policy
            </h1>
            <p class="headline mb-6 text-grey-lighten-1">
              Your privacy is important to us
            </p>
            <p class="title mb-8 text-grey-lighten-2">
              Last updated: {{ lastUpdated }}
            </p>
          </div>
        </v-col>
      </v-row>
    </v-container>

    <!-- Privacy Policy Content -->
    <v-container class="py-16">
      <v-row justify="center">
        <v-col cols="12" lg="10" xl="8">
          <v-card elevation="8" rounded="lg" class="pa-8">

            <!-- Introduction -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Introduction</h2>
              <p class="text-body-1 mb-4">
                At Cat Studio, we are committed to protecting your privacy and ensuring the security of your personal information.
                This Privacy Policy explains how we collect, use, and safeguard your information when you visit our website or use our services.
              </p>
            </section>

            <!-- Information We Collect -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Information We Collect</h2>
              <div class="mb-6">
                <h3 class="text-h6 font-weight-bold mb-3">Personal Information</h3>
                <p class="text-body-1 mb-3">
                  We may collect the following personal information when you contact us or use our services:
                </p>
                <v-list class="bg-transparent">
                  <v-list-item v-for="item in personalInfo" :key="item">
                    <template v-slot:prepend>
                      <v-icon color="primary">mdi-check-circle</v-icon>
                    </template>
                    <v-list-item-title>{{ item }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </div>

              <div class="mb-6">
                <h3 class="text-h6 font-weight-bold mb-3">Usage Information</h3>
                <p class="text-body-1 mb-3">
                  We automatically collect certain information about your interaction with our website:
                </p>
                <v-list class="bg-transparent">
                  <v-list-item v-for="item in usageInfo" :key="item">
                    <template v-slot:prepend>
                      <v-icon color="success">mdi-check-circle</v-icon>
                    </template>
                    <v-list-item-title>{{ item }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </div>
            </section>

            <!-- How We Use Information -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">How We Use Your Information</h2>
              <p class="text-body-1 mb-4">
                We use the collected information for the following purposes:
              </p>
              <v-row>
                <v-col cols="12" md="6" v-for="use in informationUses" :key="use.title">
                  <v-card class="h-100" elevation="2" rounded="lg">
                    <v-card-text class="pa-6">
                      <v-avatar size="60" :color="use.color" class="mb-4">
                        <v-icon size="30" color="white">{{ use.icon }}</v-icon>
                      </v-avatar>
                      <h4 class="text-h6 font-weight-bold mb-2">{{ use.title }}</h4>
                      <p class="text-body-2">{{ use.description }}</p>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </section>

            <!-- Information Sharing -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Information Sharing and Disclosure</h2>
              <v-alert
                type="info"
                variant="outlined"
                class="mb-4"
              >
                <v-icon start>mdi-shield-check</v-icon>
                We do not sell, trade, or otherwise transfer your personal information to third parties without your consent, except as described in this policy.
              </v-alert>
              <p class="text-body-1 mb-4">
                We may share your information only in the following circumstances:
              </p>
              <v-expansion-panels class="mb-4">
                <v-expansion-panel v-for="scenario in sharingScenarios" :key="scenario.title">
                  <v-expansion-panel-title>
                    <v-icon start :color="scenario.color">{{ scenario.icon }}</v-icon>
                    {{ scenario.title }}
                  </v-expansion-panel-title>
                  <v-expansion-panel-text>
                    {{ scenario.description }}
                  </v-expansion-panel-text>
                </v-expansion-panel>
              </v-expansion-panels>
            </section>

            <!-- Data Security -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Data Security</h2>
              <p class="text-body-1 mb-4">
                We implement appropriate technical and organizational security measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction.
              </p>
              <v-row>
                <v-col cols="12" sm="6" md="3" v-for="security in securityMeasures" :key="security.title">
                  <div class="text-center">
                    <v-avatar size="80" :color="security.color" class="mb-3">
                      <v-icon size="40" color="white">{{ security.icon }}</v-icon>
                    </v-avatar>
                    <h4 class="text-h6 font-weight-bold mb-2">{{ security.title }}</h4>
                    <p class="text-body-2">{{ security.description }}</p>
                  </div>
                </v-col>
              </v-row>
            </section>

            <!-- Your Rights -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Your Rights</h2>
              <p class="text-body-1 mb-4">
                You have the following rights regarding your personal information:
              </p>
              <v-row>
                <v-col cols="12" md="6" v-for="right in userRights" :key="right.title">
                  <v-card class="h-100" elevation="2" rounded="lg" border>
                    <v-card-text class="pa-6">
                      <div class="d-flex align-center mb-3">
                        <v-icon :color="right.color" class="mr-3">{{ right.icon }}</v-icon>
                        <h4 class="text-h6 font-weight-bold">{{ right.title }}</h4>
                      </div>
                      <p class="text-body-2">{{ right.description }}</p>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </section>

            <!-- Cookies -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Cookies and Tracking Technologies</h2>
              <p class="text-body-1 mb-4">
                We use cookies and similar tracking technologies to improve your browsing experience and analyze website traffic.
              </p>
              <v-alert
                type="warning"
                variant="outlined"
                class="mb-4"
              >
                <v-icon start>mdi-cookie</v-icon>
                You can control cookies through your browser settings. However, disabling cookies may affect the functionality of our website.
              </v-alert>
            </section>

            <!-- Contact Information -->
            <section class="mb-8">
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Contact Us</h2>
              <p class="text-body-1 mb-4">
                If you have any questions about this Privacy Policy or our data practices, please contact us:
              </p>
              <v-card elevation="2" rounded="lg" class="pa-6" color="grey-lighten-5">
                <v-row>
                  <v-col cols="12" md="6">
                    <div class="d-flex align-center mb-3">
                      <v-icon color="primary" class="mr-3">mdi-email</v-icon>
                      <span class="text-body-1">contact@catstudio.com</span>
                    </div>
                    <div class="d-flex align-center mb-3">
                      <v-icon color="primary" class="mr-3">mdi-phone</v-icon>
                      <span class="text-body-1">+1 (555) 123-4567</span>
                    </div>
                  </v-col>
                  <v-col cols="12" md="6">
                    <div class="d-flex align-center mb-3">
                      <v-icon color="primary" class="mr-3">mdi-map-marker</v-icon>
                      <span class="text-body-1">123 Design Street, Creative City, CC 12345</span>
                    </div>
                    <div class="d-flex align-center">
                      <v-icon color="primary" class="mr-3">mdi-web</v-icon>
                      <span class="text-body-1">www.catstudio.com</span>
                    </div>
                  </v-col>
                </v-row>
              </v-card>
            </section>

            <!-- Updates -->
            <section>
              <h2 class="text-h4 font-weight-bold mb-4 text-primary">Policy Updates</h2>
              <p class="text-body-1 mb-4">
                We may update this Privacy Policy from time to time. Any changes will be posted on this page with an updated revision date.
              </p>
              <v-alert
                type="info"
                variant="tonal"
                class="mb-4"
              >
                <v-icon start>mdi-bell-ring</v-icon>
                We recommend reviewing this Privacy Policy periodically to stay informed about how we protect your information.
              </v-alert>
            </section>

          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Back to Home Button -->
    <v-container class="text-center pb-8">
      <v-btn
        color="primary"
        size="large"
        rounded="lg"
        class="px-8"
        @click="$router.push('/')"
      >
        <v-icon start>mdi-home</v-icon>
        Back to Home
      </v-btn>
    </v-container>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Meta title for SEO
useHead({
  title: 'Privacy Policy - Cat Studio',
  meta: [
    { name: 'description', content: 'Cat Studio Privacy Policy - Learn how we protect and handle your personal information.' }
  ]
})

// Data
const lastUpdated = ref('December 2024')

const personalInfo = ref([
  'Name and contact information',
  'Email address',
  'Phone number',
  'Company information',
  'Project requirements and preferences'
])

const usageInfo = ref([
  'IP address and device information',
  'Browser type and version',
  'Pages visited and time spent',
  'Referring website information',
  'Geographic location (general)'
])

const informationUses = ref([
  {
    title: 'Service Delivery',
    description: 'To provide and improve our web design services',
    icon: 'mdi-cog',
    color: 'primary'
  },
  {
    title: 'Communication',
    description: 'To respond to inquiries and provide support',
    icon: 'mdi-message',
    color: 'success'
  },
  {
    title: 'Analytics',
    description: 'To analyze website usage and improve user experience',
    icon: 'mdi-chart-line',
    color: 'info'
  },
  {
    title: 'Marketing',
    description: 'To send updates about our services (with consent)',
    icon: 'mdi-bullhorn',
    color: 'warning'
  }
])

const sharingScenarios = ref([
  {
    title: 'Service Providers',
    description: 'We may share information with trusted third-party service providers who assist in operating our website and conducting our business, under strict confidentiality agreements.',
    icon: 'mdi-handshake',
    color: 'primary'
  },
  {
    title: 'Legal Requirements',
    description: 'We may disclose information when required by law or to protect our rights, property, or safety, or that of others.',
    icon: 'mdi-gavel',
    color: 'warning'
  },
  {
    title: 'Business Transfers',
    description: 'In the event of a merger, acquisition, or sale of assets, your information may be transferred as part of the business transaction.',
    icon: 'mdi-swap-horizontal',
    color: 'info'
  }
])

const securityMeasures = ref([
  {
    title: 'Encryption',
    description: 'SSL/TLS encryption for data transmission',
    icon: 'mdi-lock',
    color: 'primary'
  },
  {
    title: 'Access Control',
    description: 'Limited access to authorized personnel',
    icon: 'mdi-key',
    color: 'success'
  },
  {
    title: 'Monitoring',
    description: 'Regular security monitoring and updates',
    icon: 'mdi-shield-check',
    color: 'info'
  },
  {
    title: 'Backup',
    description: 'Secure data backup and recovery',
    icon: 'mdi-backup-restore',
    color: 'warning'
  }
])

const userRights = ref([
  {
    title: 'Access Rights',
    description: 'You can request access to the personal information we hold about you',
    icon: 'mdi-eye',
    color: 'primary'
  },
  {
    title: 'Correction Rights',
    description: 'You can request correction of inaccurate or incomplete information',
    icon: 'mdi-pencil',
    color: 'success'
  },
  {
    title: 'Deletion Rights',
    description: 'You can request deletion of your personal information in certain circumstances',
    icon: 'mdi-delete',
    color: 'error'
  },
  {
    title: 'Portability Rights',
    description: 'You can request a copy of your data in a structured, machine-readable format',
    icon: 'mdi-download',
    color: 'info'
  },
  {
    title: 'Objection Rights',
    description: 'You can object to processing of your personal information for certain purposes',
    icon: 'mdi-stop',
    color: 'warning'
  },
  {
    title: 'Consent Withdrawal',
    description: 'You can withdraw consent for data processing at any time',
    icon: 'mdi-cancel',
    color: 'purple'
  }
])
</script>

<style scoped>
.header-section {
  min-height: 40vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  position: relative;
}

.header-content {
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

section {
  scroll-margin-top: 2rem;
}

.v-expansion-panels {
  border-radius: 12px;
}

@media (max-width: 960px) {
  .header-section {
    min-height: 30vh;
  }

  .header-content {
    padding: 1rem;
  }
}
</style>
