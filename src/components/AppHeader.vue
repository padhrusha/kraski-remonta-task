<script setup>
import logo from '@/assets/logo.png'
import maxLogo from '@/assets/max-logo.png'
import timeIcon from '@/assets/time.png'
import frameIcon from '@/assets/Frame.png'
import vector1 from '@/assets/Vector 1.png'

const contacts = {
  address: 'г. Москва, Скандинавский бульвар, д. 3, к.',
  email: 'welcome@kraskiremonta.ru',
  phone: '8 993 272 17 71',
  hours: 'с 9:00 до 22:00, без выходных',
}

const navItems = [
  'Компания',
  'Ремонт',
  'Дизайн',
  'Проектирование и инжернерия',
  'Стоимость',
  'Портфолио',
]
</script>

<template>
  <header class="header">
    <div class="container header__inner">
      <div class="header__top-info">
        <span class="header__contact">
          <img class="header__contact-icon" :src="timeIcon" alt="" />
          {{ contacts.hours }}
        </span>
        <span class="header__contact">
          <img class="header__contact-icon" :src="frameIcon" alt="" />
          {{ contacts.address }}
        </span>
      </div>

      <div class="header__top-contacts">
        <span class="header__contact">
          <img class="header__max-logo" :src="maxLogo" alt="MAX" />
          MAX
        </span>
        <span class="header__contact">
          <span class="header__icon" aria-hidden="true">✉</span>
          {{ contacts.email }}
        </span>
      </div>

      <div class="header__main">
        <a class="header__logo" href="/">
          <img :src="logo" alt="Краски Ремонта" />
        </a>

        <nav class="header__nav">
          <a
            v-for="item in navItems"
            :key="item"
            class="header__nav-link"
            href="#"
          >
            {{ item }}
            <img class="header__nav-vector" :src="vector1" alt="" />
          </a>
        </nav>

        <span class="header__contact header__contact--phone header__phone">
          {{ contacts.phone }}
        </span>
      </div>

      <button class="header__cta" type="button">Оставить заявку</button>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.header {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;
  background: rgba(20, 23, 36, 0.4);
  backdrop-filter: blur(1rem);
  -webkit-backdrop-filter: blur(1rem);
  color: $color-surface;

  &__inner {
    position: relative;
    display: grid;
    grid-template-columns: 1fr auto;
    column-gap: 2rem;
    row-gap: 0;
    align-items: center;

    &::after {
      content: '';
      position: absolute;
      left: 0;
      right: 0;
      top: 2.75rem;
      height: 0.0625rem;
      background: rgba(255, 255, 255, 0.12);
      pointer-events: none;
    }
  }

  &__top-info,
  &__top-contacts {
    .header__contact {
      color: rgba(255, 255, 255, 0.5);
    }
  }

  &__top-info {
    grid-column: 1;
    grid-row: 1;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: clamp(1rem, 2vw, 2rem);
    height: 2.75rem;
    flex-wrap: nowrap;
  }

  &__top-contacts {
    grid-column: 2;
    grid-row: 1;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    justify-self: end;
    gap: 1.5rem;
    height: 2.75rem;
    flex-wrap: nowrap;
  }

  &__main {
    grid-column: 1;
    grid-row: 2;
    display: flex;
    align-items: center;
    gap: 2rem;
    height: 4rem;
  }

  &__phone {
    font-weight: 700;
    margin-left: auto;
  }

  &__cta {
    grid-column: 2;
    grid-row: 2;
    justify-self: end;
  }

  &__logo {
    display: flex;
    align-items: center;
    flex: none;

    img {
      height: 2rem;
      width: auto;
      display: block;
    }
  }

  &__nav {
    display: flex;
    align-items: center;
    gap: clamp(1rem, 2vw, 2rem);
    flex: 1;
    justify-content: center;
    flex-wrap: wrap;
  }

  &__nav-link {
    display: inline-flex;
    align-items: center;
    gap: 0.375rem;
    font-family: $font-sans;
    font-weight: 500;
    font-size: 1rem;
    line-height: 1.4;
    letter-spacing: -0.05em;
    color: $color-surface;
    transition: color 0.15s ease;

    &:hover {
      color: $color-lime;
    }
  }

  &__contact {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-family: $font-sans;
    font-weight: 400;
    font-size: 0.875rem;
    line-height: 1.4;
    letter-spacing: -0.05em;
    color: $color-surface;
  }

  &__icon {
    color: $color-accent;
    font-size: 0.875rem;
  }

  &__max-logo {
    width: 1.25rem;
    height: 1.25rem;
    border-radius: 0.25rem;
    object-fit: cover;
  }

  &__contact-icon {
    width: 1rem;
    height: 1rem;
    object-fit: contain;
  }

  &__nav-vector {
    height: 0.375rem;
    width: auto;
    object-fit: contain;
  }

  &__cta {
    background: $color-lime;
    color: $color-ink;
    font-weight: 700;
    font-size: 0.875rem;
    padding: 0.75rem 1.5rem;
    border-radius: $radius-sm;
    transition: filter 0.15s ease;

    &:hover {
      filter: brightness(0.95);
    }
  }
}
</style>
