
<template>
  <div class="page">
    <SiteHeader
      :brand="brand"
      :email="email"
      :primaryCta="{
        label: 'Let’s Talk',
        href: '#contact'
      }"
    />

    <main>
      <!-- HERO -->
      <Hero
        headline="We Build Digital Systems That "
        accent="Move Business Forward."
        subheadline="Custom backend systems, intelligent automation, and powerful admin dashboards that simplify operations and eliminate repetitive work."
        :primaryCta="{
          label: 'Discuss Your Project',
          href: '#contact'
        }"
        hint="Practical Solutions · Built Around Your Business"
      />

      <!-- PROJECTS -->
      <Projects
        title="Systems We've Built"
        :items="projects"
      />

      <!-- SERVICES / FEATURES -->
      <Features
        title="Technology That Works Behind Your Business"
        :items="features"
      />

      <!-- OUR PROCESS -->
      <section id="process" class="process-section">
        <div class="container">

          <div class="process-heading">
            <span class="eyebrow">
              <span class="eyebrow-dot"></span>
              HOW WE WORK
            </span>

            <h2>From Problem to Practical Solution.</h2>

            <p>
              A straightforward process focused on understanding your
              business and building something that actually helps.
            </p>
          </div>

          <div class="process-grid">
            <article
              v-for="step in process"
              :key="step.number"
              class="process-card"
            >
              <span class="process-number">{{ step.number }}</span>

              <div class="process-icon">
                <svg
                  v-if="step.icon === 'search'"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.6"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <circle cx="11" cy="11" r="7" />
                  <path d="m20 20-4-4" />
                </svg>

                <svg
                  v-else-if="step.icon === 'layers'"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.6"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path d="m12 3 9 5-9 5-9-5 9-5Z" />
                  <path d="m3 12 9 5 9-5" />
                  <path d="m3 16 9 5 9-5" />
                </svg>

                <svg
                  v-else
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.6"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path d="m5 12 4 4L19 6" />
                  <path d="M21 12a9 9 0 1 1-5.3-8.23" />
                </svg>
              </div>

              <h3>{{ step.title }}</h3>
              <p>{{ step.description }}</p>
            </article>
          </div>

        </div>
      </section>

      <!-- CONTACT -->
      <Contact
        id="contact"
        title="Let's Build Something Useful."
        subtitle="Tell us what slows your business down. We'll help you turn it into a simpler, smarter system."
        :whatsapp="whatsapp"
        :email="email"
      />

    </main>

    <!-- FOOTER -->
    <Footer
      :brand="brand"
      tagline="Building systems. Simplifying business."
      :email="email"
      :whatsapp="whatsapp"
    />
  </div>
</template>

<script setup>
import SiteHeader from "./components/SiteHeader.vue";
import Hero from "./components/Hero.vue";
import Projects from "./components/Projects.vue";
import Features from "./components/Features.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";

const brand = "AqilLabs";
const email = "aqillabsofficial@gmail.com";
const whatsapp = "+923122074909";

// PROJECTS
// Replace demo projects with real client projects as they become available.
const projects = [
  {
    title: "Order Management System",
    category: "BUSINESS OPERATIONS",
    status: "PROJECT DEMO",
    description:
      "A centralized dashboard for managing customer orders, tracking fulfillment, and organizing business operations.",
    image: "/demos/order-tracking.svg"
  },
  {
    title: "Clinic Management System",
    category: "ADMINISTRATIVE SYSTEMS",
    status: "PROJECT DEMO",
    description:
      "A streamlined administrative tool for organizing appointments, managing patient records, and simplifying daily workflows.",
    image: "/demos/clinic-tool.svg"
  },
  {
    title: "Inventory Management Automation",
    category: "BUSINESS AUTOMATION",
    status: "PROJECT DEMO",
    description:
      "A structured inventory solution that helps businesses monitor stock, manage products, and reduce manual updates.",
    image: "/demos/inventory-automation.svg"
  }
];

// FEATURES
const features = [
  {
    title: "Built Around Your Workflow",
    description:
      "Every solution is designed around how your business actually operates, rather than forcing you into a generic system.",
    icon: "shield"
  },
  {
    title: "Efficient Development",
    description:
      "Focused development processes deliver useful, practical systems without unnecessary complexity.",
    icon: "check"
  },
  {
    title: "Automation That Matters",
    description:
      "Reduce repetitive tasks, organize business data, and give your team more time to focus on important work.",
    icon: "chat"
  }
];

// PROCESS
const process = [
  {
    number: "01",
    title: "Understand",
    icon: "search",
    description:
      "We learn about your business, identify repetitive tasks, and understand what needs to improve."
  },
  {
    number: "02",
    title: "Build",
    icon: "layers",
    description:
      "We design and develop a practical system around your requirements and workflow."
  },
  {
    number: "03",
    title: "Deliver",
    icon: "check",
    description:
      "We test the solution, make the necessary refinements, and help you get started."
  }
];
</script>

<style scoped>
.page {
  min-height: 100vh;
  overflow: hidden;
  background: #080b12;
  color: #f8fafc;
}

/* Process section */

.process-section {
  position: relative;
  overflow: hidden;
  padding: 110px 0;
  background:
    radial-gradient(
      ellipse at 50% 100%,
      rgba(79, 70, 229, 0.09),
      transparent 55%
    ),
    #080b12;
  border-top: 1px solid rgba(255, 255, 255, 0.05);
}

.container {
  width: min(1180px, calc(100% - 48px));
  margin: 0 auto;
}

.process-heading {
  max-width: 650px;
  margin: 0 auto 55px;
  text-align: center;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 9px;
  margin-bottom: 20px;
  color: #a5b4fc;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.19em;
}

.eyebrow-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #818cf8;
  box-shadow: 0 0 12px rgba(129, 140, 248, 0.8);
}

.process-heading h2 {
  margin: 0;
  color: #f8fafc;
  font-size: clamp(30px, 4vw, 44px);
  font-weight: 750;
  letter-spacing: -0.045em;
  line-height: 1.15;
}

.process-heading > p {
  max-width: 510px;
  margin: 17px auto 0;
  color: #929bad;
  font-size: 15px;
  line-height: 1.8;
}

/* Process cards */

.process-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 22px;
}

.process-card {
  position: relative;
  padding: 30px;
  overflow: hidden;
  border: 1px solid rgba(148, 163, 184, 0.13);
  border-radius: 18px;
  background: linear-gradient(
    145deg,
    rgba(30, 41, 59, 0.58),
    rgba(15, 23, 42, 0.48)
  );
  transition:
    transform 0.3s ease,
    border-color 0.3s ease,
    background 0.3s ease;
}

.process-card:hover {
  transform: translateY(-6px);
  border-color: rgba(129, 140, 248, 0.35);
  background: rgba(30, 41, 59, 0.75);
}

.process-number {
  position: absolute;
  top: 25px;
  right: 27px;
  color: rgba(148, 163, 184, 0.35);
  font-size: 13px;
  font-weight: 750;
  letter-spacing: 0.08em;
}

.process-icon {
  display: flex;
  width: 52px;
  height: 52px;
  align-items: center;
  justify-content: center;
  margin-bottom: 27px;
  border: 1px solid rgba(129, 140, 248, 0.22);
  border-radius: 14px;
  background: rgba(99, 102, 241, 0.13);
  color: #a5b4fc;
}

.process-icon svg {
  width: 25px;
  height: 25px;
}

.process-card h3 {
  margin: 0 0 11px;
  color: #f1f5f9;
  font-size: 19px;
  font-weight: 650;
  letter-spacing: -0.025em;
}

.process-card p {
  margin: 0;
  color: #929bad;
  font-size: 14px;
  line-height: 1.8;
}

/* Responsive */

@media (max-width: 850px) {
  .process-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .process-section {
    padding: 85px 0;
  }
}

@media (max-width: 560px) {
  .container {
    width: calc(100% - 36px);
  }

  .process-section {
    padding: 75px 0;
  }

  .process-grid {
    grid-template-columns: 1fr;
    gap: 15px;
  }

  .process-card {
    padding: 25px;
  }

  .process-heading {
    margin-bottom: 38px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .process-card {
    transition: none;
  }
}
</style>
