
<template>
  <section class="hero">
    <div class="hero-glow glow-one"></div>
    <div class="hero-glow glow-two"></div>

    <div class="container hero-container">
      <!-- LEFT CONTENT -->
      <div class="hero-content">
        <div class="eyebrow">
          <span class="status-dot"></span>
          <span>SOFTWARE & BUSINESS AUTOMATION</span>
        </div>

        <h1 class="hero-title">
          {{ headline }}
          <span class="gradient-text">{{ accent }}</span>
        </h1>

        <p class="hero-description">
          {{ subheadline }}
        </p>

        <div class="hero-actions">
          <a :href="primaryCta.href" class="btn-primary">
            {{ primaryCta.label }}
            <span class="arrow">↗</span>
          </a>

          <a href="#projects" class="btn-secondary">
            Explore Our Work
            <span>↓</span>
          </a>
        </div>

        <div class="hero-note">
          <span class="note-line"></span>
          {{ hint }}
        </div>

        <div class="hero-stats">
          <div class="stat">
            <strong>01</strong>
            <span>Understand</span>
          </div>

          <div class="stat-divider"></div>

          <div class="stat">
            <strong>02</strong>
            <span>Build</span>
          </div>

          <div class="stat-divider"></div>

          <div class="stat">
            <strong>03</strong>
            <span>Improve</span>
          </div>
        </div>
      </div>

      <!-- RIGHT DASHBOARD VISUAL -->
      <div class="hero-visual">
        <div class="visual-orbit orbit-one"></div>
        <div class="visual-orbit orbit-two"></div>

        <div class="dashboard">
          <div class="dashboard-header">
            <div class="window-controls">
              <span></span>
              <span></span>
              <span></span>
            </div>

            <span class="dashboard-label">AQILLABS / CONTROL PANEL</span>

            <span class="live-status">
              <span></span>
              LIVE
            </span>
          </div>

          <div class="dashboard-body">
            <aside class="dashboard-sidebar">
              <div class="sidebar-logo">A.</div>

              <div class="sidebar-icon active">⌘</div>
              <div class="sidebar-icon">▦</div>
              <div class="sidebar-icon">↗</div>
              <div class="sidebar-icon">⚙</div>
            </aside>

            <div class="dashboard-main">
              <div class="dashboard-welcome">
                <div>
                  <span class="muted-label">WORKSPACE OVERVIEW</span>
                  <h3>Business Overview</h3>
                </div>
                <span class="date-label">Today ↗</span>
              </div>

              <div class="metric-grid">
                <div class="metric-card">
                  <span>Active Workflows</span>
                  <strong>08</strong>
                  <small class="positive">↗ Running smoothly</small>
                </div>

                <div class="metric-card">
                  <span>Tasks Automated</span>
                  <strong>124</strong>
                  <small class="positive">↗ Less manual work</small>
                </div>
              </div>

              <div class="activity-card">
                <div class="activity-heading">
                  <strong>System Activity</strong>
                  <span>RECENT EVENTS</span>
                </div>

                <div class="activity-item">
                  <span class="activity-icon blue">↗</span>
                  <div>
                    <strong>Order processed</strong>
                    <small>Order management workflow</small>
                  </div>
                  <span class="activity-time">Just now</span>
                </div>

                <div class="activity-item">
                  <span class="activity-icon purple">⌘</span>
                  <div>
                    <strong>Inventory updated</strong>
                    <small>Stock synchronization</small>
                  </div>
                  <span class="activity-time">2 min ago</span>
                </div>

                <div class="activity-item">
                  <span class="activity-icon green">✓</span>
                  <div>
                    <strong>Automation completed</strong>
                    <small>Background process</small>
                  </div>
                  <span class="activity-time">5 min ago</span>
                </div>
              </div>

              <div class="dashboard-footer">
                <span class="footer-indicator"></span>
                Systems running efficiently
                <span class="footer-version">AQIL / 01</span>
              </div>
            </div>
          </div>
        </div>

        <div class="floating-card floating-top">
          <span class="floating-icon">✳</span>
          <div>
            <strong>Smart Automation</strong>
            <small>Less manual work</small>
          </div>
        </div>

        <div class="floating-card floating-bottom">
          <span class="floating-icon purple-icon">⌘</span>
          <div>
            <strong>Custom Systems</strong>
            <small>Built for your workflow</small>
          </div>
        </div>
      </div>
    </div>

    <div class="hero-bottom">
      <div class="container bottom-inner">
        <span>DESIGNED FOR BETTER OPERATIONS</span>
        <span class="bottom-line"></span>
        <span>BACKEND SYSTEMS · DASHBOARDS · AUTOMATION</span>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  headline: { type: String, required: true },
  accent: { type: String, required: true },
  subheadline: { type: String, required: true },
  primaryCta: { type: Object, required: true },
  hint: { type: String, default: "" }
});
</script>

<style scoped>
.hero {
  position: relative;
  min-height: 760px;
  padding: 110px 0 0;
  overflow: hidden;
  background:
    radial-gradient(ellipse at 75% 35%, rgba(37, 99, 235, .12), transparent 40%),
    linear-gradient(135deg, #080b12 0%, #0b1020 55%, #090d17 100%);
  color: #fff;
}

.hero-container {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 1fr 1.05fr;
  align-items: center;
  gap: 65px;
  padding-bottom: 100px;
}

.hero-glow {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  pointer-events: none;
}

.glow-one {
  width: 300px;
  height: 300px;
  background: rgba(37, 99, 235, .12);
  top: 10%;
  left: -150px;
}

.glow-two {
  width: 350px;
  height: 350px;
  background: rgba(124, 58, 237, .11);
  bottom: 0;
  right: -150px;
}

.hero-content {
  max-width: 600px;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  padding: 10px 15px;
  border: 1px solid rgba(148, 163, 184, .18);
  border-radius: 100px;
  background: rgba(255, 255, 255, .035);
  color: #a5b4fc;
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 1.8px;
}

.status-dot,
.live-status span,
.footer-indicator {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #4ade80;
  box-shadow: 0 0 12px rgba(74, 222, 128, .6);
}

.hero-title {
  margin: 28px 0 22px;
  color: #f8fafc;
  font-size: clamp(42px, 5.1vw, 66px);
  line-height: 1.08;
  letter-spacing: -3.5px;
  font-weight: 750;
}

.gradient-text {
  display: inline;
  background: linear-gradient(110deg, #60a5fa, #818cf8 55%, #c4b5fd);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.hero-description {
  max-width: 510px;
  color: #94a3b8;
  font-size: 16px;
  line-height: 1.9;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 14px;
  margin-top: 34px;
}

.btn-primary,
.btn-secondary {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  padding: 15px 21px;
  border-radius: 9px;
  text-decoration: none;
  font-size: 13px;
  font-weight: 700;
  transition: .3s ease;
}

.btn-primary {
  color: white;
  background: linear-gradient(110deg, #2563eb, #6366f1);
  box-shadow: 0 10px 35px rgba(37, 99, 235, .25);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 14px 40px rgba(37, 99, 235, .4);
}

.arrow {
  font-size: 17px;
}

.btn-secondary {
  color: #cbd5e1;
  border: 1px solid rgba(148, 163, 184, .2);
  background: rgba(255, 255, 255, .025);
}

.btn-secondary:hover {
  border-color: #647de9;
  background: rgba(99, 102, 241, .1);
}

.hero-note {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: 20px;
  color: #64748b;
  font-size: 11px;
}

.note-line {
  width: 25px;
  height: 1px;
  background: #6366f1;
}

.hero-stats {
  display: flex;
  align-items: center;
  gap: 25px;
  margin-top: 55px;
}

.stat {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.stat strong {
  color: #e2e8f0;
  font-size: 20px;
  letter-spacing: -1px;
}

.stat span {
  color: #64748b;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.stat-divider {
  height: 30px;
  width: 1px;
  background: rgba(148, 163, 184, .2);
}

/* DASHBOARD */

.hero-visual {
  position: relative;
  min-width: 0;
  perspective: 1200px;
}

.dashboard {
  position: relative;
  z-index: 2;
  overflow: hidden;
  border: 1px solid rgba(148, 163, 184, .2);
  border-radius: 15px;
  background: #0f1725;
  box-shadow: 0 35px 100px rgba(0, 0, 0, .45);
  transform: rotateY(-5deg) rotateX(2deg);
  animation: dashboard-float 7s ease-in-out infinite;
}

.dashboard-header {
  height: 47px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 17px;
  border-bottom: 1px solid rgba(148, 163, 184, .12);
  background: #111b2b;
}

.window-controls {
  display: flex;
  gap: 5px;
}

.window-controls span {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #475569;
}

.window-controls span:first-child {
  background: #f87171;
}

.window-controls span:nth-child(2) {
  background: #fbbf24;
}

.window-controls span:nth-child(3) {
  background: #4ade80;
}

.dashboard-label {
  color: #64748b;
  font-size: 8px;
  letter-spacing: 1.4px;
}

.live-status {
  display: flex;
  align-items: center;
  gap: 7px;
  color: #86efac;
  font-size: 8px;
  font-weight: 700;
}

.live-status span {
  width: 5px;
  height: 5px;
}

.dashboard-body {
  display: flex;
  min-height: 340px;
}

.dashboard-sidebar {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 22px;
  width: 58px;
  padding: 18px 0;
  border-right: 1px solid rgba(148, 163, 184, .12);
  background: #111b2b;
}

.sidebar-logo {
  display: grid;
  place-items: center;
  width: 29px;
  height: 29px;
  margin-bottom: 10px;
  border-radius: 8px;
  color: white;
  background: linear-gradient(135deg, #2563eb, #818cf8);
  font-weight: 800;
}

.sidebar-icon {
  display: grid;
  place-items: center;
  width: 30px;
  height: 30px;
  border-radius: 7px;
  color: #64748b;
  font-size: 15px;
}

.sidebar-icon.active {
  color: #93c5fd;
  background: rgba(59, 130, 246, .16);
}

.dashboard-main {
  flex: 1;
  min-width: 0;
  padding: 23px;
}

.dashboard-welcome {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  margin-bottom: 22px;
}

.muted-label {
  color: #64748b;
  font-size: 8px;
  letter-spacing: 1.4px;
}

.dashboard-welcome h3 {
  margin: 7px 0 0;
  color: #f1f5f9;
  font-size: 17px;
}

.date-label {
  color: #94a3b8;
  font-size: 9px;
  padding: 7px 10px;
  border: 1px solid rgba(148, 163, 184, .15);
  border-radius: 6px;
}

.metric-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.metric-card {
  padding: 15px;
  border: 1px solid rgba(148, 163, 184, .13);
  border-radius: 9px;
  background: #131f31;
}

.metric-card > span {
  display: block;
  color: #94a3b8;
  font-size: 9px;
}

.metric-card strong {
  display: block;
  margin: 10px 0 6px;
  color: #f8fafc;
  font-size: 27px;
  letter-spacing: -1px;
}

.metric-card small {
  font-size: 8px;
}

.positive {
  color: #4ade80;
}

.activity-card {
  margin-top: 15px;
  padding: 15px;
  border: 1px solid rgba(148, 163, 184, .13);
  border-radius: 9px;
  background: #131f31;
}

.activity-heading {
  display: flex;
  justify-content: space-between;
  margin-bottom: 13px;
}

.activity-heading strong {
  color: #e2e8f0;
  font-size: 10px;
}

.activity-heading span {
  color: #64748b;
  font-size: 7px;
  letter-spacing: 1px;
}

.activity-item {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px 0;
  border-top: 1px solid rgba(148, 163, 184, .08);
}

.activity-icon {
  display: grid;
  place-items: center;
  width: 27px;
  height: 27px;
  flex-shrink: 0;
  border-radius: 7px;
  font-size: 12px;
}

.activity-icon.blue {
  color: #60a5fa;
  background: rgba(59, 130, 246, .13);
}

.activity-icon.purple {
  color: #c4b5fd;
  background: rgba(139, 92, 246, .13);
}

.activity-icon.green {
  color: #4ade80;
  background: rgba(34, 197, 94, .13);
}

.activity-item div {
  display: flex;
  flex: 1;
  flex-direction: column;
  gap: 4px;
  min-width: 0;
}

.activity-item strong {
  color: #e2e8f0;
  font-size: 9px;
}

.activity-item small,
.activity-time {
  color: #64748b;
  font-size: 8px;
}

.activity-time {
  white-space: nowrap;
}

.dashboard-footer {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-top: 16px;
  color: #94a3b8;
  font-size: 8px;
}

.footer-indicator {
  width: 5px;
  height: 5px;
}

.footer-version {
  margin-left: auto;
  color: #475569;
  letter-spacing: 1px;
}

.floating-card {
  position: absolute;
  z-index: 3;
  display: flex;
  align-items: center;
  gap: 11px;
  padding: 13px 16px;
  border: 1px solid rgba(148, 163, 184, .2);
  border-radius: 11px;
  background: rgba(17, 27, 43, .94);
  backdrop-filter: blur(15px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, .3);
  animation: card-float 5s ease-in-out infinite;
}

.floating-top {
  top: -30px;
  right: -20px;
}

.floating-bottom {
  bottom: 30px;
  left: -35px;
  animation-delay: -2s;
}

.floating-icon {
  display: grid;
  place-items: center;
  width: 34px;
  height: 34px;
  border-radius: 8px;
  color: #93c5fd;
  background: rgba(59, 130, 246, .15);
  font-size: 17px;
}

.purple-icon {
  color: #c4b5fd;
  background: rgba(139, 92, 246, .15);
}

.floating-card div {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.floating-card strong {
  color: #e2e8f0;
  font-size: 10px;
}

.floating-card small {
  color: #64748b;
  font-size: 8px;
}

.visual-orbit {
  position: absolute;
  border: 1px solid rgba(99, 102, 241, .13);
  border-radius: 50%;
  pointer-events: none;
}

.orbit-one {
  width: 460px;
  height: 460px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.orbit-two {
  width: 560px;
  height: 560px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.hero-bottom {
  position: relative;
  z-index: 2;
  border-top: 1px solid rgba(148, 163, 184, .12);
  background: rgba(255, 255, 255, .015);
}

.bottom-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  min-height: 65px;
  color: #64748b;
  font-size: 9px;
  font-weight: 700;
  letter-spacing: 1.5px;
}

.bottom-line {
  flex: 1;
  max-width: 180px;
  height: 1px;
  background: rgba(148, 163, 184, .2);
}

@keyframes dashboard-float {
  0%, 100% { transform: rotateY(-5deg) rotateX(2deg) translateY(0); }
  50% { transform: rotateY(-5deg) rotateX(2deg) translateY(-9px); }
}

@keyframes card-float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-9px); }
}

/* TABLET */
@media (max-width: 1024px) {
  .hero-container {
    gap: 35px;
    grid-template-columns: 1fr 1fr;
  }

  .hero-title {
    font-size: clamp(40px, 5vw, 54px);
  }

  .floating-top {
    right: -5px;
  }

  .floating-bottom {
    left: -10px;
  }
}

/* MOBILE */
@media (max-width: 768px) {
  .hero {
    padding-top: 75px;
  }

  .hero-container {
    grid-template-columns: 1fr;
    gap: 65px;
    padding-bottom: 85px;
  }

  .hero-content {
    max-width: 100%;
  }

  .hero-title {
    font-size: clamp(39px, 10vw, 55px);
    letter-spacing: -2px;
  }

  .hero-description {
    font-size: 14px;
  }

  .hero-stats {
    margin-top: 38px;
  }

  .hero-visual {
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
  }

  .dashboard {
    transform: none;
    animation: none;
  }

  .floating-top {
    top: -30px;
    right: 0;
  }

  .floating-bottom {
    bottom: -30px;
    left: 0;
  }

  .bottom-inner {
    flex-wrap: wrap;
    justify-content: center;
    padding: 20px 0;
    text-align: center;
    font-size: 8px;
  }

  .bottom-line {
    display: none;
  }

  .orbit-one {
    width: 350px;
    height: 350px;
  }

  .orbit-two {
    width: 420px;
    height: 420px;
  }
}

@media (max-width: 480px) {
  .dashboard-main {
    padding: 14px;
  }

  .dashboard-sidebar {
    width: 42px;
  }

  .dashboard-body {
    min-height: 310px;
  }

  .metric-card {
    padding: 10px;
  }

  .metric-card strong {
    font-size: 22px;
  }

  .activity-time {
    display: none;
  }

  .floating-card {
    padding: 10px;
  }

  .floating-card strong {
    font-size: 9px;
  }

  .hero-actions {
    align-items: stretch;
  }

  .btn-primary,
  .btn-secondary {
    padding: 14px;
    font-size: 11px;
  }
}
</style>
