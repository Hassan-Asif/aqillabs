
<template>
  <header class="header">
    <div class="container header-inner">

      <!-- BRAND -->
      <a href="#" class="brand" aria-label="AqilLabs Home">
        <!-- <span class="brand-mark">A</span> -->
        <span class="brand-name">{{ brand }}</span>
        <!-- <span class="brand-dot">.</span> -->
      </a>

      <!-- DESKTOP NAVIGATION -->
      <nav class="desktop-nav">
        <a href="#services" class="nav-link">Services</a>
        <a href="#projects" class="nav-link">Our Work</a>
        <a href="#process" class="nav-link">Process</a>
        <a href="#contact" class="nav-link">About / Contact</a>
      </nav>

      <!-- ACTIONS -->
      <div class="header-actions">
        <a :href="'mailto:' + email" class="email-link">
          <span class="email-icon">✉</span>
          <span>Let's Talk</span>
        </a>

        <a :href="primaryCta.href" class="header-cta">
          {{ primaryCta.label }}
          <span>↗</span>
        </a>

        <!-- MOBILE MENU BUTTON -->
        <button
          class="menu-toggle"
          type="button"
          :aria-expanded="menuOpen"
          aria-label="Toggle navigation menu"
          @click="menuOpen = !menuOpen"
        >
          <span :class="{ active: menuOpen }"></span>
          <span :class="{ active: menuOpen }"></span>
        </button>
      </div>
    </div>

    <!-- MOBILE NAVIGATION -->
    <Transition name="menu">
      <nav v-if="menuOpen" class="mobile-nav">
        <a href="#services" @click="closeMenu">Services</a>
        <a href="#projects" @click="closeMenu">Our Work</a>
        <a href="#process" @click="closeMenu">Process</a>
        <a href="#contact" @click="closeMenu">Contact</a>

        <a :href="'mailto:' + email" class="mobile-email">
          {{ email }}
        </a>
      </nav>
    </Transition>

    <div class="header-border"></div>
  </header>
</template>

<script setup>
import { ref } from "vue";

defineProps({
  brand: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true
  },
  primaryCta: {
    type: Object,
    default: () => ({
      label: "Contact Us",
      href: "#contact"
    })
  }
});

const menuOpen = ref(false);

const closeMenu = () => {
  menuOpen.value = false;
};
</script>

<style scoped>
.header {
  position: sticky;
  top: 0;
  z-index: 100;
  width: 100%;
  background: rgba(8, 11, 18, .86);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
}

.header-inner {
  min-height: 82px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 30px;
}

/* BRAND */

.brand {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  text-decoration: none;
  flex-shrink: 0;
}

.brand-mark {
  display: grid;
  place-items: center;
  width: 36px;
  height: 36px;
  border-radius: 10px;
  color: #fff;
  background: linear-gradient(135deg, #2563eb, #818cf8);
  font-size: 19px;
  font-weight: 800;
  box-shadow: 0 5px 20px rgba(59, 130, 246, .25);
}

.brand-name {
  color: #f8fafc;
  font-size: 20px;
  font-weight: 800;
  letter-spacing: -1px;
}

.brand-dot {
  margin-left: -10px;
  color: #818cf8;
  font-size: 23px;
  font-weight: 800;
}

/* DESKTOP NAV */

.desktop-nav {
  display: flex;
  align-items: center;
  gap: 33px;
}

.nav-link {
  position: relative;
  color: #94a3b8;
  font-size: 12px;
  font-weight: 600;
  text-decoration: none;
  transition: color .25s ease;
}

.nav-link::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -8px;
  width: 0;
  height: 2px;
  border-radius: 10px;
  background: #818cf8;
  transition: width .25s ease;
}

.nav-link:hover {
  color: #fff;
}

.nav-link:hover::after {
  width: 100%;
}

/* HEADER ACTIONS */

.header-actions {
  display: flex;
  align-items: center;
  gap: 12px;
}

.email-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 12px;
  color: #cbd5e1;
  font-size: 12px;
  font-weight: 600;
  text-decoration: none;
  transition: color .25s ease;
}

.email-link:hover {
  color: #fff;
}

.email-icon {
  color: #818cf8;
  font-size: 15px;
}

.header-cta {
  display: inline-flex;
  align-items: center;
  gap: 15px;
  padding: 12px 17px;
  border: 1px solid rgba(129, 140, 248, .35);
  border-radius: 8px;
  color: #fff;
  background: linear-gradient(110deg, #2563eb, #6366f1);
  font-size: 12px;
  font-weight: 700;
  text-decoration: none;
  box-shadow: 0 5px 20px rgba(37, 99, 235, .15);
  transition: all .25s ease;
}

.header-cta:hover {
  transform: translateY(-2px);
  box-shadow: 0 9px 25px rgba(99, 102, 241, .3);
}

.header-cta span {
  font-size: 16px;
}

/* MOBILE MENU BUTTON */

.menu-toggle {
  display: none;
  width: 42px;
  height: 42px;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 6px;
  border: 1px solid rgba(148, 163, 184, .2);
  border-radius: 8px;
  background: rgba(255, 255, 255, .04);
  cursor: pointer;
}

.menu-toggle span {
  width: 17px;
  height: 2px;
  border-radius: 5px;
  background: #e2e8f0;
  transition: .25s ease;
}

.menu-toggle span:first-child.active {
  transform: translateY(4px) rotate(45deg);
}

.menu-toggle span:last-child.active {
  transform: translateY(-4px) rotate(-45deg);
}

/* MOBILE NAV */

.mobile-nav {
  display: none;
}

.header-border {
  height: 1px;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(99, 102, 241, .35),
    rgba(148, 163, 184, .12),
    transparent
  );
}

/* ANIMATION */

.menu-enter-active,
.menu-leave-active {
  transition: all .25s ease;
}

.menu-enter-from,
.menu-leave-to {
  opacity: 0;
  transform: translateY(-8px);
}

/* RESPONSIVE */

@media (max-width: 900px) {
  .desktop-nav {
    gap: 18px;
  }

  .nav-link {
    font-size: 11px;
  }

  .email-link {
    display: none;
  }
}

@media (max-width: 720px) {
  .header-inner {
    min-height: 72px;
  }

  .desktop-nav {
    display: none;
  }

  .menu-toggle {
    display: flex;
  }

  .mobile-nav {
    display: flex;
    flex-direction: column;
    gap: 5px;
    padding: 12px 24px 22px;
    border-top: 1px solid rgba(148, 163, 184, .1);
    background: #0b1020;
  }

  .mobile-nav > a {
    padding: 13px 10px;
    border-radius: 7px;
    color: #cbd5e1;
    font-size: 14px;
    font-weight: 600;
    text-decoration: none;
    transition: .2s ease;
  }

  .mobile-nav > a:hover {
    color: #fff;
    background: rgba(99, 102, 241, .1);
  }

  .mobile-nav .mobile-email {
    margin-top: 8px;
    border-top: 1px solid rgba(148, 163, 184, .12);
    border-radius: 0;
    color: #818cf8;
    font-size: 12px;
  }
}

@media (max-width: 420px) {
  .brand-name {
    font-size: 18px;
  }

  .header-cta {
    padding: 11px 12px;
    gap: 7px;
    font-size: 11px;
  }
}
</style>
