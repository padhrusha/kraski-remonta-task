<script setup>
import { ref } from 'vue'
import vector1 from '@/assets/Vector 1.png'
import ruFlag from '@/assets/russian_flag.png'

const faqs = [
  {
    q: 'Кто у вас работает?',
    a: 'Наша команда — практикующие юристы с опытом ведения дел против застройщиков и подрядчиков от 5 лет.',
  },
  {
    q: 'Как происходит оплата?',
    a: 'Мы фиксируем стоимость в договоре. Возможна поэтапная оплата по мере прохождения дела.',
  },
  {
    q: 'Кто покупает материалы?',
    a: 'В рамках юридического сопровождения материалы не закупаются — это услуга по правовой поддержке.',
  },
  {
    q: 'Есть ли у вас лицензия на выполнение ремонтно-отделочных работ?',
    a: 'Да. У нас есть разрешения на оказание всех видов услуг по ремонту квартир.\nНеобходимая документация представлена на сайте.',
  },
]

const open = ref(-1)
const form = ref({ phone: '', message: '' })

function toggle(i) {
  open.value = open.value === i ? -1 : i
}

function submit() {
  console.log('faq submit', form.value)
}
</script>

<template>
  <section class="faq">
    <div class="container">
      <h2 class="faq__title">Часто задаваемые вопросы</h2>

      <div class="faq__grid">
        <div class="faq__list">
          <article
            v-for="(f, i) in faqs"
            :key="f.q"
            class="faq__item"
            :class="{ 'faq__item--open': open === i }"
          >
            <button class="faq__head" type="button" @click="toggle(i)">
              <span>{{ f.q }}</span>
              <span class="faq__chevron" aria-hidden="true">
                <img :src="vector1" alt="" />
              </span>
            </button>
            <div v-if="open === i" class="faq__body">
              <p v-for="(line, j) in f.a.split('\n')" :key="j">{{ line }}</p>
            </div>
          </article>
        </div>

        <aside class="faq__form">
          <h3 class="faq__form-title">У меня есть вопрос</h3>
          <form @submit.prevent="submit">
            <div class="faq__input-wrap">
              <img class="faq__flag" :src="ruFlag" alt="RU" />
              <input
                v-model="form.phone"
                class="faq__input"
                type="tel"
                placeholder="+7 (000) 000-00-00"
              />
            </div>
            <textarea
              v-model="form.message"
              class="faq__input faq__input--area"
              placeholder="Ваш вопрос"
              rows="6"
            ></textarea>
            <button type="submit" class="faq__submit">Оставить заявку</button>
          </form>
        </aside>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.faq {
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
    grid-template-columns: 1fr 27rem;
    gap: 2rem;
    align-items: start;
  }

  &__list {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  &__item {
    background: $color-surface;
    border-radius: $radius-sm;
    overflow: hidden;
  }

  &__head {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    padding: 1.375rem 1.75rem;
    text-align: left;
    font-weight: 700;
    font-size: 1rem;
  }

  &__chevron {
    width: 2rem;
    height: 2rem;
    display: grid;
    place-items: center;
    border-radius: $radius-sm;
    background: $color-bg;
    transition: transform 0.2s ease;

    img {
      width: 0.75rem;
      height: auto;
      object-fit: contain;
      filter: invert(1);
    }

    .faq__item--open & {
      transform: rotate(180deg);
    }
  }

  &__body {
    padding: 0 1.75rem 1.375rem;
    font-size: 0.875rem;
    line-height: 1.5;
    color: $color-ink;

    p {
      margin: 0 0 0.25rem;
    }
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

  &__input-wrap {
    position: relative;
    margin-bottom: 0.75rem;
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

  &__input {
    width: 100%;
    background: $color-surface;
    border: 0;
    border-radius: $radius-sm;
    padding: 0.875rem 1rem 0.875rem 2.75rem;
    font-size: 1rem;
    outline: none;

    &::placeholder {
      color: rgba(20, 23, 36, 0.4);
    }

    &--area {
      padding: 0.875rem 1rem;
      resize: vertical;
      min-height: 11rem;
      font-family: inherit;
    }
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
