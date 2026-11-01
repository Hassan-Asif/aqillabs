
<template>
  <section id="projects" class="projects-section">
    <div class="container">

      <!-- SECTION HEADER -->
      <div class="section-heading">
        <div class="eyebrow">
          <span class="eyebrow-dot"></span>
          OUR SELECTED WORK
        </div>

        <div class="heading-row">
          <div>
            <h2 class="section-title">
              {{ title }}
              <span class="title-accent">.</span>
            </h2>

            <p class="section-description">
              Practical digital solutions designed to simplify
              operations and help businesses work smarter.
            </p>
          </div>

          <div class="work-count">
            <strong>0{{ items.length }}</strong>
            <span>PROJECTS</span>
          </div>
        </div>
      </div>

      <!-- PROJECT GRID -->
      <div class="projects-grid">
        <article
          v-for="(p, idx) in items"
          :key="idx"
          class="project-card"
        >
          <!-- PROJECT IMAGE -->
          <div class="project-visual">

            <div class="visual-top">
              <span class="project-number">
                PROJECT / 0{{ idx + 1 }}
              </span>

              <span class="project-arrow">↗</span>
            </div>

            <img
              v-if="p.image"
              :src="p.image"
              :alt="p.title"
              loading="lazy"
              class="project-image"
            />

            <div v-else class="image-fallback">
              <span>AL.</span>
            </div>

            <div class="visual-bottom">
              <span class="visual-label">AQILLABS STUDIO</span>
              <span class="visual-line"></span>
            </div>
          </div>

          <!-- PROJECT DETAILS -->
          <div class="project-body">

            <div class="project-meta">
              <span class="project-category">
                {{ p.category || "BUSINESS SYSTEMS" }}
              </span>

              <span class="project-status">
                <span></span>
                COMPLETED
              </span>
            </div>

            <h3 class="project-title">
              {{ p.title }}
            </h3>

            <p class="project-description">
              {{ p.description }}
            </p>

            <div class="project-footer">
              <span>Explore project</span>
              <span class="footer-arrow">↗</span>
            </div>

          </div>
        </article>
      </div>

      <!-- BOTTOM MESSAGE -->
      <div class="projects-bottom">
        <span>HAVE A PROJECT IN MIND?</span>

        <a href="#contact">
          Let's build it together
          <span>↗</span>
        </a>
      </div>

    </div>
  </section>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    default: "Selected Work"
  },
  items: {
    type: Array,
    default: () => []
  }
});
</script>

<style scoped>
.projects-section {
  position: relative;
  padding: 115px 0;
  overflow: hidden;
  color: #f8fafc;
  background: #080b12;
}

/* SECTION HEADING */

.section-heading {
  margin-bottom: 55px;
}

.eyebrow {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 20px;
  color: #818cf8;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 2px;
}

.eyebrow-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #818cf8;
  box-shadow: 0 0 12px rgba(129, 140, 248, .6);
}

.heading-row {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  gap: 30px;
}

.section-title {
  margin: 0;
  color: #f8fafc;
  font-size: clamp(36px, 5vw, 54px);
  font-weight: 750;
  letter-spacing: -2.5px;
}

.title-accent {
  color: #818cf8;
}

.section-description {
  max-width: 510px;
  margin: 15px 0 0;
  color: #94a3b8;
  font-size: 14px;
  line-height: 1.8;
}

.work-count {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 5px;
  padding-bottom: 5px;
}

.work-count strong {
  color: #e2e8f0;
  font-size: 30px;
  letter-spacing: -1px;
}

.work-count span {
  color: #64748b;
  font-size: 9px;
  font-weight: 700;
  letter-spacing: 1.5px;
}

/* PROJECT GRID */

.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 23px;
}

.project-card {
  min-width: 0;
  overflow: hidden;
  border: 1px solid rgba(148, 163, 184, .14);
  border-radius: 13px;
  background: #0e1421;
  transition:
    transform .35s ease,
    border-color .35s ease,
    box-shadow .35s ease;
}

.project-card:hover {
  transform: translateY(-8px);
  border-color: rgba(129, 140, 248, .45);
  box-shadow: 0 25px 55px rgba(0, 0, 0, .28);
}

/* PROJECT VISUAL */

.project-visual {
  position: relative;
  height: 220px;
  overflow: hidden;
  background:
    radial-gradient(circle at 70% 50%, rgba(79, 70, 229, .2), transparent 45%),
    linear-gradient(135deg, #17233a, #101827 60%, #141329);
}

.project-visual::after {
  content: "";
  position: absolute;
  inset: 0;
  pointer-events: none;
  background: linear-gradient(
    180deg,
    rgba(8, 11, 18, .25),
    transparent 30%,
    transparent 70%,
    rgba(8, 11, 18, .4)
  );
}

.project-image {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  padding: 42px 18px;
  object-fit: contain;
  transition: transform .6s ease;
}

.project-card:hover .project-image {
  transform: scale(1.06);
}

.visual-top,
.visual-bottom {
  position: absolute;
  z-index: 2;
  left: 18px;
  right: 18px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.visual-top {
  top: 17px;
}

.project-number,
.visual-label {
  color: #94a3b8;
  font-size: 8px;
  font-weight: 700;
  letter-spacing: 1.5px;
}

.project-arrow {
  display: grid;
  place-items: center;
  width: 29px;
  height: 29px;
  border: 1px solid rgba(148, 163, 184, .25);
  border-radius: 50%;
  color: #cbd5e1;
  background: rgba(15, 23, 42, .5);
  transition: .3s ease;
}

.project-card:hover .project-arrow {
  color: white;
  background: #4f46e5;
  border-color: #6366f1;
  transform: rotate(45deg);
}

.visual-bottom {
  bottom: 15px;
}

.visual-line {
  width: 45px;
  height: 1px;
  background: rgba(129, 140, 248, .6);
}

.image-fallback {
  position: absolute;
  inset: 0;
  display: grid;
  place-items: center;
}

.image-fallback span {
  color: rgba(129, 140, 248, .4);
  font-size: 85px;
  font-weight: 900;
  letter-spacing: -10px;
}

/* PROJECT BODY */

.project-body {
  padding: 22px;
}

.project-meta {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
}

.project-category {
  color: #a5b4fc;
  font-size: 8px;
  font-weight: 800;
  letter-spacing: 1.3px;
}

.project-status {
  display: flex;
  align-items: center;
  gap: 6px;
  color: #64748b;
  font-size: 8px;
  font-weight: 700;
}

.project-status span {
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: #4ade80;
}

.project-title {
  margin: 19px 0 10px;
  color: #f1f5f9;
  font-size: 19px;
  font-weight: 700;
  letter-spacing: -.5px;
  transition: color .3s ease;
}

.project-card:hover .project-title {
  color: #a5b4fc;
}

.project-description {
  min-height: 67px;
  margin: 0;
  color: #94a3b8;
  font-size: 12px;
  line-height: 1.8;
}

.project-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 22px;
  padding-top: 16px;
  border-top: 1px solid rgba(148, 163, 184, .12);
  color: #64748b;
  font-size: 10px;
  font-weight: 700;
  transition: color .3s ease;
}

.project-card:hover .project-footer {
  color: #a5b4fc;
}

.footer-arrow {
  font-size: 17px;
}

/* BOTTOM MESSAGE */

.projects-bottom {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  margin-top: 50px;
  padding-top: 24px;
  border-top: 1px solid rgba(148, 163, 184, .12);
}

.projects-bottom > span {
  color: #64748b;
  font-size: 9px;
  font-weight: 800;
  letter-spacing: 1.5px;
}

.projects-bottom a {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  color: #a5b4fc;
  font-size: 12px;
  font-weight: 700;
  text-decoration: none;
  transition: gap .25s ease;
}

.projects-bottom a:hover {
  gap: 18px;
}

/* RESPONSIVE */

@media (max-width: 950px) {
  .projects-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 600px) {
  .projects-section {
    padding: 80px 0;
  }

  .heading-row {
    align-items: flex-start;
  }

  .section-title {
    font-size: 39px;
  }

  .work-count {
    display: none;
  }

  .projects-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }

  .project-visual {
    height: 220px;
  }

  .project-description {
    min-height: auto;
  }

  .projects-bottom {
    align-items: flex-start;
    flex-direction: column;
    gap: 15px;
  }
}
</style>
