
<template>
  <section class="contact-section">
    <div class="container">
      <div class="contact-card" :id="id">

        <!-- Background effects -->
        <div class="glow glow-one"></div>
        <div class="glow glow-two"></div>

        <div class="contact-content">
          <!-- Heading -->
          <span class="eyebrow">
            <span class="eyebrow-dot"></span>
            LET'S TALK
          </span>

          <h2 class="contact-title">
            {{ title }}
          </h2>

          <p class="contact-subtitle">
            {{ subtitle }}
          </p>

          <!-- Actions -->
          <div class="actions">
            <a
              class="btn btn-primary"
              :href="waLink"
              target="_blank"
              rel="noopener noreferrer"
            >
              <svg
                viewBox="0 0 24 24"
                fill="currentColor"
                aria-hidden="true"
              >
                <path d="M20.52 3.48A11.85 11.85 0 0 0 12.08 0C5.5 0 .15 5.35.15 11.93c0 2.1.55 4.15 1.6 5.96L0 24l6.27-1.65a11.9 11.9 0 0 0 5.8 1.48h.01c6.57 0 11.92-5.35 11.92-11.93 0-3.18-1.24-6.17-3.48-8.42ZM12.08 21.8a9.9 9.9 0 0 1-5.05-1.39l-.36-.21-3.72.98.99-3.63-.24-.37a9.84 9.84 0 0 1-1.51-5.25c0-5.46 4.44-9.9 9.9-9.9a9.84 9.84 0 0 1 7 2.9 9.84 9.84 0 0 1 2.9 7c0 5.45-4.45 9.87-9.91 9.87Zm5.43-7.4c-.3-.15-1.76-.87-2.03-.97-.27-.1-.47-.15-.67.15-.2.3-.77.97-.94 1.17-.17.2-.35.22-.65.07-.3-.15-1.26-.46-2.4-1.47-.89-.8-1.49-1.78-1.66-2.08-.17-.3-.02-.46.13-.61.13-.13.3-.35.45-.52.15-.17.2-.3.3-.5.1-.2.05-.37-.03-.52-.08-.15-.67-1.62-.92-2.22-.24-.58-.49-.5-.67-.51h-.57c-.2 0-.52.07-.8.37-.27.3-1.04 1.02-1.04 2.49 0 1.47 1.07 2.89 1.22 3.09.15.2 2.1 3.2 5.08 4.49.71.3 1.26.49 1.69.63.71.23 1.36.2 1.87.12.57-.08 1.76-.72 2.01-1.42.25-.7.25-1.3.17-1.42-.07-.12-.27-.2-.57-.35Z"/>
              </svg>
              <span>Start a Conversation</span>
              <span class="btn-arrow">↗</span>
            </a>

            <a
              class="btn btn-secondary"
              :href="'mailto:' + email"
            >
              <svg
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.7"
                stroke-linecap="round"
                stroke-linejoin="round"
                aria-hidden="true"
              >
                <rect x="3" y="5" width="18" height="14" rx="2" />
                <path d="m3 7 9 6 9-6" />
              </svg>
              <span>Email Us</span>
            </a>
          </div>

          <!-- Contact note -->
          <div class="contact-note">
            <span class="note-icon">✦</span>
            <p>
              Tell us what you need — an admin dashboard, business automation,
              or a system built around your workflow.
            </p>
          </div>
        </div>

        <!-- Bottom details -->
        <div class="contact-bottom">
          <span>BUILT AROUND YOUR BUSINESS</span>
          <span class="bottom-divider"></span>
          <span>LET'S MAKE WORK SIMPLER</span>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const props = defineProps({
  id: {
    type: String,
    default: "contact"
  },
  title: {
    type: String,
    default: "Let's Build Something Useful."
  },
  subtitle: {
    type: String,
    default: "Have a project in mind? Tell us what you're working on."
  },
  whatsapp: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true
  }
});

const waLink = `https://wa.me/${props.whatsapp.replace(/[^0-9]/g, "")}?text=${encodeURIComponent(
  "Hi AqilLabs! I'd like to discuss a project."
)}`;
</script>

<style scoped>
.contact-section {
  position: relative;
  overflow: hidden;
  padding: 110px 0;
  background: #090d17;
  color: #f8fafc;
}

.container {
  width: min(1180px, calc(100% - 48px));
  margin: 0 auto;
}

/* Main card */

.contact-card {
  position: relative;
  isolation: isolate;
  overflow: hidden;
  padding: 85px 35px 28px;
  border: 1px solid rgba(129, 140, 248, 0.2);
  border-radius: 26px;
  background:
    linear-gradient(
      135deg,
      rgba(30, 41, 72, 0.94),
      rgba(13, 19, 35, 0.98) 55%,
      rgba(18, 25, 48, 0.96)
    );
  box-shadow: 0 30px 90px rgba(0, 0, 0, 0.28);
  text-align: center;
}

/* Background glow */

.glow {
  position: absolute;
  z-index: -1;
  border-radius: 50%;
  pointer-events: none;
  filter: blur(80px);
}

.glow-one {
  top: -180px;
  left: 20%;
  width: 420px;
  height: 300px;
  background: rgba(79, 70, 229, 0.2);
}

.glow-two {
  right: -120px;
  bottom: -180px;
  width: 350px;
  height: 350px;
  background: rgba(37, 99, 235, 0.13);
}

/* Content */

.contact-content {
  position: relative;
  max-width: 720px;
  margin: 0 auto;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 9px;
  margin-bottom: 22px;
  color: #a5b4fc;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.2em;
}

.eyebrow-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #818cf8;
  box-shadow: 0 0 12px rgba(129, 140, 248, 0.8);
}

.contact-title {
  margin: 0;
  color: #fff;
  font-size: clamp(32px, 5vw, 52px);
  font-weight: 750;
  letter-spacing: -0.05em;
  line-height: 1.12;
}

.contact-subtitle {
  max-width: 570px;
  margin: 20px auto 0;
  color: #a1aabd;
  font-size: 15px;
  line-height: 1.8;
}

/* Buttons */

.actions {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 14px;
  margin-top: 34px;
}

.btn {
  display: inline-flex;
  min-height: 54px;
  align-items: center;
  justify-content: center;
  gap: 11px;
  padding: 0 23px;
  border-radius: 12px;
  font-size: 14px;
  font-weight: 650;
  text-decoration: none;
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease,
    border-color 0.25s ease,
    background 0.25s ease;
}

.btn svg {
  width: 19px;
  height: 19px;
  flex-shrink: 0;
}

.btn-primary {
  color: white;
  background: linear-gradient(110deg, #6366f1, #3b82f6);
  box-shadow: 0 8px 25px rgba(79, 70, 229, 0.25);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 13px 35px rgba(79, 70, 229, 0.38);
}

.btn-secondary {
  color: #e2e8f0;
  border: 1px solid rgba(148, 163, 184, 0.24);
  background: rgba(255, 255, 255, 0.045);
}

.btn-secondary:hover {
  transform: translateY(-3px);
  border-color: rgba(165, 180, 252, 0.5);
  background: rgba(255, 255, 255, 0.08);
}

.btn-arrow {
  margin-left: 3px;
  font-size: 17px;
  transition: transform 0.25s ease;
}

.btn-primary:hover .btn-arrow {
  transform: translate(3px, -3px);
}

/* Contact note */

.contact-note {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  max-width: 580px;
  margin: 35px auto 0;
  padding: 15px 20px;
  border: 1px solid rgba(148, 163, 184, 0.1);
  border-radius: 12px;
  background: rgba(2, 6, 23, 0.22);
}

.note-icon {
  flex-shrink: 0;
  color: #a5b4fc;
  font-size: 15px;
}

.contact-note p {
  margin: 0;
  color: #9ca8ba;
  font-size: 12px;
  line-height: 1.7;
}

/* Bottom details */

.contact-bottom {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-top: 55px;
  padding-top: 23px;
  border-top: 1px solid rgba(148, 163, 184, 0.12);
  color: #66738a;
  font-size: 9px;
  font-weight: 700;
  letter-spacing: 0.16em;
}

.bottom-divider {
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: #818cf8;
}

/* Responsive */

@media (max-width: 600px) {
  .contact-section {
    padding: 75px 0;
  }

  .container {
    width: calc(100% - 32px);
  }

  .contact-card {
    padding: 65px 20px 22px;
    border-radius: 20px;
  }

  .contact-title {
    font-size: 35px;
  }

  .contact-subtitle {
    font-size: 14px;
  }

  .actions {
    flex-direction: column;
    gap: 12px;
  }

  .btn {
    width: 100%;
  }

  .contact-note {
    align-items: flex-start;
    padding: 13px;
    text-align: left;
  }

  .contact-bottom {
    gap: 9px;
    margin-top: 38px;
    font-size: 8px;
    letter-spacing: 0.08em;
  }
}

@media (prefers-reduced-motion: reduce) {
  .btn,
  .btn-arrow {
    transition: none;
  }
}
</style>
