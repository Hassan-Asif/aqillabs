
<template>
  <section id="services" class="features-section">
    <div class="container">

      <!-- Section heading -->
      <div class="section-heading">
        <span class="eyebrow">
          <span class="eyebrow-dot"></span>
          WHAT WE DO
        </span>

        <h2 class="section-title">
          {{ title }}
        </h2>

        <p class="section-description">
          Practical technology, thoughtfully built to make your everyday
          business operations easier.
        </p>
      </div>

      <!-- Feature cards -->
      <div class="features-grid">
        <article
          v-for="(f, idx) in items"
          :key="idx"
          class="feature-card"
        >
          <div class="card-top">
            <div class="icon-wrap">
              <svg
                v-if="f.icon === 'shield'"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.6"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M12 22s8-4 8-11V5l-8-3-8 3v6c0 7 8 11 8 11Z" />
                <path d="m9 12 2 2 4-4" />
              </svg>

              <svg
                v-else-if="f.icon === 'check'"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.6"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M12 22s8-4 8-11V5l-8-3-8 3v6c0 7 8 11 8 11Z" />
                <path d="m9 12 2 2 4-4" />
              </svg>

              <svg
                v-else-if="f.icon === 'chat'"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.6"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M21 11.5a8.4 8.4 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.4 8.4 0 0 1-3.8-.9L3 21l1.9-5.7a8.4 8.4 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.4 8.4 0 0 1 3.8-.9h.5a8.5 8.5 0 0 1 8 8v.5Z" />
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
                <path d="M12 3v18" />
                <path d="m5 10 7-7 7 7" />
                <path d="M5 14h14" />
              </svg>
            </div>

            <span class="feature-number">
              0{{ idx + 1 }}
            </span>
          </div>

          <h3 class="feature-title">
            {{ f.title }}
          </h3>

          <p class="feature-description">
            {{ f.description }}
          </p>

          <div class="card-line"></div>
        </article>
      </div>

      <!-- Bottom note -->
      <div class="features-footer">
        <span class="footer-line"></span>
        <p>Simple solutions. Better workflows. Less manual work.</p>
        <span class="footer-line"></span>
      </div>

    </div>
  </section>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    default: "Technology That Works Behind Your Business"
  },
  items: {
    type: Array,
    default: () => []
  }
});
</script>

<style scoped>
.features-section {
  position: relative;
  overflow: hidden;
  padding: 110px 0;
  background:
    radial-gradient(
      ellipse at 50% 0%,
      rgba(79, 70, 229, 0.10),
      transparent 55%
    ),
    #090d17;
  border-top: 1px solid rgba(255, 255, 255, 0.06);
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
  color: #f8fafc;
}

.features-section::before {
  content: "";
  position: absolute;
  width: 420px;
  height: 420px;
  top: 25%;
  left: -300px;
  border-radius: 50%;
  background: rgba(59, 130, 246, 0.08);
  filter: blur(100px);
  pointer-events: none;
}

.container {
  position: relative;
  z-index: 1;
  width: min(1180px, calc(100% - 48px));
  margin: 0 auto;
}

/* Heading */

.section-heading {
  max-width: 680px;
  margin: 0 auto 58px;
  text-align: center;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 9px;
  margin-bottom: 20px;
  color: #9ca3af;
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

.section-title {
  margin: 0;
  color: #f8fafc;
  font-size: clamp(30px, 4vw, 46px);
  line-height: 1.15;
  font-weight: 750;
  letter-spacing: -0.045em;
}

.section-description {
  max-width: 540px;
  margin: 18px auto 0;
  color: #929bad;
  font-size: 15px;
  line-height: 1.8;
}

/* Cards */

.features-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 22px;
}

.feature-card {
  position: relative;
  min-height: 245px;
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
    transform 0.35s ease,
    border-color 0.35s ease,
    background 0.35s ease,
    box-shadow 0.35s ease;
}

.feature-card::before {
  content: "";
  position: absolute;
  top: -100px;
  right: -100px;
  width: 190px;
  height: 190px;
  border-radius: 50%;
  background: rgba(99, 102, 241, 0.09);
  filter: blur(55px);
  opacity: 0;
  transition: opacity 0.35s ease;
}

.feature-card:hover {
  transform: translateY(-7px);
  border-color: rgba(129, 140, 248, 0.35);
  background: linear-gradient(
    145deg,
    rgba(35, 48, 75, 0.75),
    rgba(17, 24, 39, 0.7)
  );
  box-shadow: 0 20px 55px rgba(0, 0, 0, 0.22);
}

.feature-card:hover::before {
  opacity: 1;
}

.card-top {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 32px;
}

.icon-wrap {
  display: flex;
  width: 54px;
  height: 54px;
  align-items: center;
  justify-content: center;
  border: 1px solid rgba(129, 140, 248, 0.22);
  border-radius: 15px;
  background: linear-gradient(
    145deg,
    rgba(99, 102, 241, 0.17),
    rgba(59, 130, 246, 0.08)
  );
  color: #a5b4fc;
  transition: transform 0.35s ease;
}

.icon-wrap svg {
  width: 25px;
  height: 25px;
}

.feature-card:hover .icon-wrap {
  transform: scale(1.08) rotate(-4deg);
}

.feature-number {
  color: rgba(148, 163, 184, 0.35);
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.08em;
}

.feature-title {
  position: relative;
  margin: 0 0 12px;
  color: #f1f5f9;
  font-size: 19px;
  font-weight: 650;
  letter-spacing: -0.025em;
}

.feature-description {
  position: relative;
  max-width: 310px;
  margin: 0;
  color: #929bad;
  font-size: 14px;
  line-height: 1.8;
}

.card-line {
  position: absolute;
  bottom: 0;
  left: 30px;
  width: 35px;
  height: 2px;
  border-radius: 10px;
  background: linear-gradient(90deg, #818cf8, #3b82f6);
  opacity: 0.7;
  transition: width 0.35s ease;
}

.feature-card:hover .card-line {
  width: calc(100% - 60px);
}

/* Footer */

.features-footer {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 18px;
  margin-top: 48px;
}

.features-footer p {
  margin: 0;
  color: #778397;
  font-size: 12px;
  letter-spacing: 0.04em;
  text-align: center;
}

.footer-line {
  width: 45px;
  height: 1px;
  background: rgba(148, 163, 184, 0.2);
}

/* Responsive */

@media (max-width: 850px) {
  .features-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .features-section {
    padding: 85px 0;
  }
}

@media (max-width: 560px) {
  .container {
    width: min(100% - 36px, 1180px);
  }

  .features-grid {
    grid-template-columns: 1fr;
    gap: 15px;
  }

  .feature-card {
    min-height: auto;
    padding: 25px;
  }

  .card-top {
    margin-bottom: 25px;
  }

  .section-heading {
    margin-bottom: 38px;
  }

  .features-footer {
    gap: 10px;
    margin-top: 35px;
  }

  .footer-line {
    width: 20px;
    flex-shrink: 0;
  }

  .features-footer p {
    font-size: 11px;
  }
}
</style>
