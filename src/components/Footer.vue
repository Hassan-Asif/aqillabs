
<template>
  <footer class="footer">
    <div class="container">

      <!-- Main footer -->
      <div class="footer-main">

        <!-- Brand -->
        <div class="footer-brand">
          <a href="#" class="brand">
            <!-- <span class="brand-mark">A</span> -->
            <span class="brand-name">{{ brand }}</span>
          </a>

          <p class="brand-description">
            {{ tagline }}
          </p>

          <p class="brand-detail">
            We build practical digital systems that simplify business
            operations and reduce repetitive work.
          </p>
        </div>

        <!-- Navigation -->
        <div class="footer-column">
          <h3>EXPLORE</h3>
          <a href="#">Home</a>
          <a href="#services">What We Do</a>
          <a href="#projects">Our Work</a>
          <a href="#contact">Contact</a>
        </div>

        <!-- Services -->
        <div class="footer-column">
          <h3>WHAT WE BUILD</h3>
          <a href="#services">Admin Dashboards</a>
          <a href="#services">Business Automation</a>
          <a href="#services">Backend Systems</a>
          <a href="#services">Internal Tools</a>
        </div>

        <!-- Contact -->
        <div class="footer-column">
          <h3>GET IN TOUCH</h3>

          <a :href="'mailto:' + email">
            {{ email }}
          </a>

          <a
            v-if="whatsapp"
            :href="waLink"
            target="_blank"
            rel="noopener noreferrer"
          >
            WhatsApp Us ↗
          </a>

          <a href="#contact" class="footer-contact-link">
            Start a Project <span>↗</span>
          </a>
        </div>

      </div>

      <!-- Bottom bar -->
      <div class="footer-bottom">
        <div class="copyright">
          © {{ year }} <strong>{{ brand }}</strong>. All rights reserved.
        </div>

        <div class="footer-bottom-right">
          <span>Built with purpose.</span>
          <span class="status-dot"></span>
          <span>Made to simplify work.</span>
        </div>
      </div>

    </div>
  </footer>
</template>

<script setup>
import { computed } from "vue";

const year = new Date().getFullYear();

const props = defineProps({
  brand: {
    type: String,
    required: true
  },
  tagline: {
    type: String,
    default: "Building systems. Simplifying business."
  },
  email: {
    type: String,
    default: "aqillabs@gmail.com"
  },
  whatsapp: {
    type: String,
    default: ""
  }
});

const waLink = computed(() => {
  const number = props.whatsapp.replace(/[^0-9]/g, "");

  return number
    ? `https://wa.me/${number}?text=${encodeURIComponent(
        "Hi AqilLabs! I'd like to discuss a project."
      )}`
    : "";
});
</script>

<style scoped>
.footer {
  position: relative;
  padding: 75px 0 25px;
  overflow: hidden;
  background: #080b13;
  color: #f8fafc;
}

.container {
  width: min(1180px, calc(100% - 48px));
  margin: 0 auto;
}

/* Main layout */

.footer-main {
  display: grid;
  grid-template-columns: 1.5fr 0.8fr 1fr 1fr;
  gap: 55px;
  padding-bottom: 65px;
}

/* Brand */

.brand {
  display: inline-flex;
  align-items: center;
  gap: 11px;
  color: #fff;
  text-decoration: none;
}

.brand-mark {
  display: flex;
  width: 38px;
  height: 38px;
  align-items: center;
  justify-content: center;
  border: 1px solid rgba(129, 140, 248, 0.4);
  border-radius: 11px;
  background: linear-gradient(
    135deg,
    #6366f1,
    #3b82f6
  );
  box-shadow: 0 5px 20px rgba(79, 70, 229, 0.25);
  color: #fff;
  font-size: 19px;
  font-weight: 800;
}

.brand-name {
  font-size: 20px;
  font-weight: 750;
  letter-spacing: -0.04em;
}

.brand-description {
  margin: 20px 0 9px;
  color: #cbd5e1;
  font-size: 14px;
  font-weight: 600;
}

.brand-detail {
  max-width: 290px;
  margin: 0;
  color: #7f8ba0;
  font-size: 13px;
  line-height: 1.8;
}

/* Footer columns */

.footer-column {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 15px;
}

.footer-column h3 {
  margin: 7px 0 8px;
  color: #a5b4fc;
  font-size: 10px;
  font-weight: 750;
  letter-spacing: 0.16em;
}

.footer-column a {
  color: #8e9aad;
  font-size: 13px;
  text-decoration: none;
  transition: color 0.25s ease, transform 0.25s ease;
}

.footer-column a:hover {
  color: #fff;
  transform: translateX(3px);
}

.footer-contact-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  margin-top: 5px;
  color: #a5b4fc !important;
  font-weight: 650;
}

.footer-contact-link span {
  transition: transform 0.25s ease;
}

.footer-contact-link:hover span {
  transform: translate(3px, -3px);
}

/* Bottom bar */

.footer-bottom {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  padding-top: 23px;
  border-top: 1px solid rgba(148, 163, 184, 0.12);
}

.copyright {
  color: #69758a;
  font-size: 12px;
}

.copyright strong {
  color: #cbd5e1;
  font-weight: 650;
}

.footer-bottom-right {
  display: flex;
  align-items: center;
  gap: 9px;
  color: #69758a;
  font-size: 11px;
}

.status-dot {
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: #818cf8;
  box-shadow: 0 0 9px rgba(129, 140, 248, 0.7);
}

/* Responsive */

@media (max-width: 900px) {
  .footer-main {
    grid-template-columns: 1.3fr 1fr 1fr;
    gap: 40px;
  }

  .footer-brand {
    grid-column: 1 / -1;
  }
}

@media (max-width: 600px) {
  .footer {
    padding: 60px 0 22px;
  }

  .container {
    width: calc(100% - 36px);
  }

  .footer-main {
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 38px 22px;
    padding-bottom: 40px;
  }

  .footer-brand {
    grid-column: 1 / -1;
  }

  .brand-detail {
    max-width: 100%;
  }

  .footer-column {
    gap: 13px;
  }

  .footer-column a {
    font-size: 12px;
  }

  .footer-bottom {
    align-items: flex-start;
    flex-direction: column;
    gap: 13px;
  }

  .footer-bottom-right {
    font-size: 10px;
  }
}
</style>
