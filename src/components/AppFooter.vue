<script setup>
import logo from '@/assets/logo_black.png'
import maxLogo from '@/assets/max-logo.png'
import personalAccount from '@/assets/personal_account.png'

const columnsTop = [
  {
    title: 'Компания',
    items: [
      'О нас',
      'Социальная ответственность',
      'Карьера',
      'Партнерам',
      'Юридическое сопровождение',
      'Блог',
      'Контакты',
    ],
  },
  {
    title: 'Ремонт жилых помещений',
    items: [
      'Квартиры',
      'Коттеджи',
      'Таунхаусы',
      'Загородный дом',
      'Этапы работ',
      'Контроль за ремонтом',
      'Гарантия и страхование ремонта',
    ],
  },
  {
    title: 'Ремонт коммерческих помещений',
    items: [
      'Офисы',
      'Отели',
      'Магазины',
      'Фитнес-центры',
      'Склады',
      'Салоны красоты',
      'Рестораны и кафе',
      'Медицинские центры',
    ],
  },
  {
    title: 'Дизайн',
    items: [
      'Архитектура и дизайн',
      'Жилые интерьеры',
      'Интерьеры для бизнеса',
      'Авторские надзоры',
      'Подбор материалов',
      'Мебелировка и комплектация',
    ],
  },
]

const columnsBottom = [
  {
    title: 'Проектирование и инженерия',
    items: [
      'Инженерные проекты',
      'Управление строительством',
      'Промышленное проектирование',
      'Обследование зданий',
      'Команда под проект',
      'Технический надзор',
    ],
  },
  {
    title: 'Стоимость',
    items: [
      'Ремонт под ключ',
      'Архитектура и дизайн',
      'Проектирование и инженерия',
      'Прайс лист',
    ],
  },
  {
    title: 'Портфолио',
    items: [
      'Фотографии жилого интерьера',
      'Фотографии коммерческого интерьера',
      'Видео-обзоры объектов',
    ],
  },
]

const legalLeft = [
  { text: 'Публичная оферта', underline: true },
  { text: 'Политика конфиденциальности', underline: true },
  { text: 'Правовая информация', underline: true },
]

const legalMiddle = [
  { text: 'Правила организации выполнения работ по ремонту', underline: true },
  { text: '«Покупка со сбером» в кредит', underline: true },
  { text: 'Оплата', underline: true },
]

const disclaimer = `Обработка персональных данных Пользователя осуществляется в соответствии с законодательством Российской Федерации. Администрация Сайта обрабатывает персональные данные Пользователя в целях осуществления обратной связи. Заполняя форму «Фамилия, Имя, Отчество», «Электронная почта», «Телефон», «Город» и иные сведения, Пользователь даёт согласие на обработку своих персональных данных — имени, адреса электронной почты и телефона. Под обработкой персональных данных понимается сбор, систематизация, накопление, уточнение (обновление, изменение). Вся информация, размещённая на данном сайте, включая стоимости товаров и (или) услуг, ни при каких условиях не является офертой, публичной офертой, договором и публичным договором определяемыми положениями статьей 426, 435 и 437 и 494 ГК РФ или заверениями об обязательствах. Любая информация, представленная на данном сайте, носит исключительно информационный характер.`
</script>

<template>
  <footer class="footer">
    <div class="container footer__inner">
      <div class="footer__top">
        <a class="footer__logo" href="/">
          <img :src="logo" alt="Краски Ремонта" />
        </a>
        <span class="footer__contact">
          <span class="footer__contact-icon" aria-hidden="true"></span>
          г. Москва, Скандинавский бульвар, д. 3, к.
        </span>
        <span class="footer__contact">
          <span class="footer__icon" aria-hidden="true">✉</span>
          welcome@kraskiremonta.ru
        </span>
        <span class="footer__contact footer__contact--phone">8 993 272 17 71</span>
        <span class="footer__contact">
          <img class="footer__max-logo" :src="maxLogo" alt="MAX" />
          MAX
        </span>
      </div>

      <div class="footer__columns footer__columns--top">
        <div v-for="col in columnsTop" :key="col.title" class="footer__col">
          <h4 class="footer__col-title">{{ col.title }}</h4>
          <ul class="footer__list">
            <li v-for="i in col.items" :key="i">
              <a href="#">{{ i }}</a>
            </li>
          </ul>
        </div>
      </div>

      <div class="footer__columns footer__columns--bottom">
        <div v-for="col in columnsBottom" :key="col.title" class="footer__col">
          <h4 class="footer__col-title">{{ col.title }}</h4>
          <ul class="footer__list">
            <li v-for="i in col.items" :key="i">
              <a href="#">{{ i }}</a>
            </li>
          </ul>
        </div>

        <div class="footer__col footer__col--account">
          <span class="footer__account">
            <img class="footer__account-icon" :src="personalAccount" alt="" />
            Личный кабинет
          </span>
        </div>
      </div>

      <div class="footer__legal">
        <div class="footer__legal-col">
          <p class="footer__copy">© 2004–2025 «Краски Ремонта»</p>
          <ul class="footer__legal-list">
            <li v-for="l in legalLeft" :key="l.text">
              <a href="#" :class="{ 'is-underline': l.underline }">{{ l.text }}</a>
            </li>
          </ul>
        </div>

        <ul class="footer__legal-list footer__legal-list--mid">
          <li v-for="l in legalMiddle" :key="l.text">
            <a href="#" :class="{ 'is-underline': l.underline }">{{ l.text }}</a>
          </li>
        </ul>

        <div class="footer__company">
          <p>ООО «ДОМЕО МАРКЕТИНГ»</p>
          <p>ИНН 9704067054</p>
          <p>ОГРН 1217700244717</p>
        </div>
      </div>

      <p class="footer__disclaimer">{{ disclaimer }}</p>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  background: $color-surface;
  color: $color-ink;
  width: 100%;

  &__inner {
    padding-top: clamp(2.5rem, 6vw, 7rem);
    padding-bottom: clamp(2.5rem, 5vw, 6rem);
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: clamp(1.25rem, 2.5vw, 3rem);
    padding-bottom: clamp(3rem, 6vw, 6rem);
    flex-wrap: wrap;
    width: 100%;
    max-width: 80rem;
  }

  &__logo {
    display: flex;
    align-items: center;

    img {
      height: 2rem;
      width: auto;
      display: block;
    }
  }

  &__contact {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.875rem;
    font-weight: 600;

    &--phone {
      font-weight: 700;
    }
  }

  &__icon {
    color: $color-accent;
  }

  &__max-logo {
    width: 1.25rem;
    height: 1.25rem;
    border-radius: 0.25rem;
    object-fit: cover;
  }

  &__contact-icon {
    display: inline-block;
    width: 1rem;
    height: 1rem;
    background-color: $color-accent;
    mask: url('@/assets/Frame.png') no-repeat center / contain;
    -webkit-mask: url('@/assets/Frame.png') no-repeat center / contain;
  }

  &__columns {
    display: grid;
    gap: clamp(1.5rem, 5vw, 6rem);
    width: 100%;
    max-width: 80rem;

    &--top {
      grid-template-columns: repeat(4, minmax(0, 1fr));
      padding-bottom: clamp(2.5rem, 5vw, 6rem);

      @media (max-width: 56rem) {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
      @media (max-width: 30rem) {
        grid-template-columns: 1fr;
      }
    }

    &--bottom {
      grid-template-columns: repeat(4, minmax(0, 1fr));
      padding-bottom: clamp(2.5rem, 5vw, 6rem);

      @media (max-width: 56rem) {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
      @media (max-width: 30rem) {
        grid-template-columns: 1fr;
      }
    }
  }

  &__col-title {
    font-size: 1.25rem;
    font-weight: 700;
    line-height: 1.4;
    margin: 0 0 1.5rem;
  }

  &__list {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 1rem;

    a {
      font-size: 1rem;
      line-height: 1.4;

      &:hover {
        color: $color-accent;
      }
    }
  }

  &__col--account {
    grid-column: 4;

    @media (max-width: 56rem) {
      grid-column: auto;
    }
  }

  &__account {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    font-size: 1.25rem;
    font-weight: 700;

    &-icon {
      width: 1.75rem;
      height: 1.75rem;
      display: block;
      object-fit: contain;
    }
  }

  &__legal {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: clamp(1.5rem, 5vw, 6rem);
    padding-bottom: 2rem;
    color: $color-ink-50;
    font-size: 0.75rem;
    width: 100%;
    max-width: 80rem;

    @media (max-width: 56rem) {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
    @media (max-width: 30rem) {
      grid-template-columns: 1fr;
    }
  }

  &__legal-col {
    grid-column: 1;

    @media (max-width: 56rem) {
      grid-column: auto;
    }
  }

  &__legal-list--mid {
    grid-column: 2;

    @media (max-width: 56rem) {
      grid-column: auto;
    }
  }


  &__copy {
    margin: 0 0 0.75rem;
  }

  &__legal-list {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    font-size: 0.75rem;

    a.is-underline {
      text-decoration: underline;
    }
  }

  &__company {
    grid-column: 4;

    p {
      margin: 0 0 0.25rem;
    }

    @media (max-width: 56rem) {
      grid-column: auto;
    }
  }

  &__disclaimer {
    font-size: 0.75rem;
    line-height: 1.5;
    color: $color-ink-50;
    margin: 0;
    width: 100%;
    max-width: 80rem;
  }
}
</style>
