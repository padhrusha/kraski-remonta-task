<script setup>
import heroUrl from '@/assets/hero.jpg'

const description = `Претензий в случае нарушений застройщиком сроков сдачи объектов, несоответствия жилья технической и проектной документации, и иных разногласия нередко решаются в судебном порядке. Немногие строительные фирмы готовы в добровольном порядке идти на мирное досудебное соглашение и выплату компенсаций, снижение стоимости или устранение ошибок. В компании «Идет ремонт» вы можете заказать услуги по юридическому сопровождению споров с недвижимостью в суде. Наши специалисты соберут необходимые документы, будут участвовать в заседаниях. Работаем с объектами в Москве и Московской области. Все вопросы уточняйте у менеджеров.`
</script>

<template>
  <section class="hero" :style="{ backgroundImage: `url(${heroUrl})` }">
    <div class="hero__overlay"></div>
    <div class="container hero__inner">
      <nav class="hero__breadcrumbs" aria-label="breadcrumbs">
        <a href="/">Главная</a>
        <span class="hero__breadcrumb-sep">/</span>
        <span>Юридическое сопровождение</span>
      </nav>
      <h1 class="hero__title">Юридическое сопровождение</h1>
      <p class="hero__description">{{ description }}</p>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero {
  position: relative;
  min-height: 40rem;
  background-color: #2a2d3a;
  background-size: cover;
  background-position: top center;
  background-repeat: no-repeat;
  color: $color-surface;
  display: flex;
  align-items: center;
  overflow: hidden;

  &__overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(
      90deg,
      rgba(20, 23, 36, 0.85) 0%,
      rgba(20, 23, 36, 0.5) 45%,
      rgba(20, 23, 36, 0) 100%
    );
    pointer-events: none;
  }

  &__inner {
    position: relative;
    z-index: 1;
    padding-top: 12.5rem;
    padding-bottom: 7.5rem;
  }

  &__breadcrumbs {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.875rem;
    margin-bottom: 1.5rem;

    a {
      color: rgba(255, 255, 255, 0.5);

      &:hover {
        color: $color-lime;
      }
    }
  }

  &__breadcrumb-sep {
    color: rgba(255, 255, 255, 0.5);
  }

  &__title {
    font-family: 'Druk Cyr', 'Druk', $font-display;
    font-weight: 700;
    font-size: 5rem;
    line-height: 1;
    letter-spacing: 0.03em;
    text-transform: uppercase;
    margin: 0 0 2rem;
  }

  &__description {
    max-width: 47.5rem;
    font-size: 1rem;
    line-height: 1.5;
    margin: 0;
    opacity: 0.9;
  }
}
</style>
