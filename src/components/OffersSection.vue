<script setup>
const offers = [
  { num: '01', text: 'Полноценную консультацию у нашего юриста.' },
  { num: '02', text: 'Составление претензии к застройщику или ремонтной бригаде' },
  { num: '03', text: 'Представительство на судебных заседаниях первой и второй инстанции' },
  { num: '04', text: 'Получение исполнительного листа, его предоставление в банк или приставам' },
  { num: '05', text: 'Подготовка и подача заявлений о банкротстве застройщика.' },
]

const note = `В случае необходимости у нас же вы можете заказать приёмку квартиры или частного дома после строительства или ремонта, обследование с помощью тепловизора и иного специального оборудования. Мы выявим существующие дефекты, составим подробный отчёт, который может быть использован в судебных разбирательствах.`
</script>

<template>
  <section class="offers">
    <div class="container">
      <h2 class="offers__title">Мы предлагаем</h2>
      <div class="offers__grid">
        <article v-for="o in offers" :key="o.num" class="offers__card">
          <div class="offers__num">{{ o.num }}</div>
          <p class="offers__text">{{ o.text }}</p>
        </article>
        <p class="offers__note">{{ note }}</p>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.offers {
  padding: 2.5rem 0 5rem;

  &__title {
    font-family: $font-display;
    font-size: 2.25rem;
    font-weight: 400;
    text-transform: uppercase;
    margin: 0 0 2rem;
    letter-spacing: 0.01em;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr) 1fr;
    gap: 1rem;
    align-items: stretch;
  }

  &__card {
    background: $color-surface;
    border-radius: $radius-sm;
    padding: 1.5rem;
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  &__num {
    font-family: $font-display;
    font-size: 2rem;
    color: $color-accent;
    line-height: 1;
  }

  &__text {
    font-size: 0.875rem;
    line-height: 1.4;
    margin: 0;
  }

  &__note {
    font-size: 0.75rem;
    line-height: 1.5;
    margin: 0;
    padding: 0;
  }
}
</style>
