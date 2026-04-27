<script setup>
import { ref } from 'vue'
import ruFlag from '@/assets/russian_flag.png'

const disputes = [
  { name: 'Несоблюдение сроков сдачи объекта застройщиком', price: 'от 30 000 ₽' },
  { name: 'Некачественные строительные и отделочные работы', price: 'от 30 000 ₽' },
  { name: 'Споры по приёмке и подписанию акта приёма-передачи', price: 'от 30 000 ₽' },
  { name: 'Возврат денежных средств за расторгнутый ДДУ', price: 'от 50 000 ₽' },
  { name: 'Признание права собственности через суд', price: 'от 50 000 ₽' },
  { name: 'Споры с управляющей компанией и ТСЖ', price: 'от 30 000 ₽' },
]

const form = ref({ name: '', phone: '', message: '' })

function submit() {
  console.log('submit', form.value)
}
</script>

<template>
  <section class="disputes">
    <div class="container disputes__inner">
      <h2 class="disputes__title">
        Виды споров с застройщиком по ДДУ и стоимость услуг
      </h2>

      <div class="disputes__grid">
        <div class="disputes__table" role="table">
          <div class="disputes__row disputes__row--head" role="row">
            <span role="columnheader">Услуга</span>
            <span role="columnheader">Цена</span>
          </div>
          <div
            v-for="d in disputes"
            :key="d.name"
            class="disputes__row"
            role="row"
          >
            <span role="cell">{{ d.name }}</span>
            <span role="cell" class="disputes__price">{{ d.price }}</span>
          </div>
        </div>

        <aside class="disputes__form">
          <h3 class="disputes__form-title">Оставить заявку</h3>
          <form @submit.prevent="submit">
            <input
              v-model="form.name"
              class="disputes__input"
              type="text"
              placeholder="Имя"
            />
            <div class="disputes__input-wrap">
              <img class="disputes__flag" :src="ruFlag" alt="RU" />
              <input
                v-model="form.phone"
                class="disputes__input disputes__input--phone"
                type="tel"
                placeholder="+7 (000) 000-00-00"
              />
            </div>
            <textarea
              v-model="form.message"
              class="disputes__input disputes__input--area"
              placeholder="Ваш вопрос"
              rows="3"
            ></textarea>
            <button type="submit" class="disputes__submit">Оставить заявку</button>
          </form>
        </aside>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "sass:color";

.disputes {
  padding: 5rem 0;

  &__title {
    font-size: 1.75rem;
    font-weight: 700;
    line-height: 1.2;
    margin: 0 0 2rem;
  }

  &__grid {
    display: grid;
    grid-template-columns: 1fr 27rem;
    gap: 2rem;
    align-items: start;
  }

  &__table {
    background: $color-surface;
    border-radius: $radius-sm;
    overflow: hidden;
  }

  &__row {
    display: grid;
    grid-template-columns: 1fr 12.5rem;
    gap: 1.5rem;
    padding: 1.125rem 2rem;
    border-bottom: 0.0625rem solid $color-divider;
    font-size: 1rem;

    &:last-child {
      border-bottom: 0;
    }

    &--head {
      font-weight: 700;
      background: color.adjust($color-bg, $lightness: 1%);
    }
  }

  &__price {
    font-weight: 600;
  }

  &__form {
    background: $color-lime;
    border-radius: $radius-sm;
    padding: 2rem;
  }

  &__form-title {
    font-family: $font-display;
    font-size: 1.75rem;
    font-weight: 400;
    margin: 0 0 1.5rem;
    text-transform: uppercase;
  }

  &__input {
    width: 100%;
    background: $color-surface;
    border: 0;
    border-radius: $radius-sm;
    padding: 0.875rem 1rem;
    font-size: 1rem;
    margin-bottom: 0.75rem;
    outline: none;

    &::placeholder {
      color: rgba(20, 23, 36, 0.4);
    }

    &--phone {
      padding-left: 2.75rem;
    }

    &--area {
      resize: vertical;
      min-height: 6rem;
      font-family: inherit;
    }
  }

  &__input-wrap {
    position: relative;
    margin-bottom: 0.75rem;

    .disputes__input {
      margin-bottom: 0;
    }
  }

  &__flag {
    position: absolute;
    left: 0.875rem;
    top: 50%;
    transform: translateY(-50%);
    width: 1.375rem;
    height: auto;
    border-radius: 0.125rem;
    object-fit: contain;
  }

  &__submit {
    width: 100%;
    background: $color-accent;
    color: $color-surface;
    font-weight: 700;
    padding: 1rem;
    border-radius: $radius-sm;
    margin-top: 0.5rem;

    &:hover {
      filter: brightness(1.05);
    }
  }
}
</style>
