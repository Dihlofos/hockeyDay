<script setup>
const partners = [
  {
    src: '/images/logos/project.svg',
    alt: 'Проект Мэра Москвы',
    width: 85,
    href: 'https://www.mos.ru/city/projects/',
  },
  {
    src: '/images/logos/zima.svg',
    alt: 'Зима в Москве',
    width: 107,
    href: 'https://zima.mos.ru/',
  },
  {
    src: '/images/logos/department.svg',
    alt: 'Департамент спорта города Москвы',
    width: 122,
    href: 'https://www.mos.ru/moskomsport/',
  },
  {
    src: '/images/logos/mossport.svg',
    alt: 'Московский спорт',
    width: 147,
    href: 'https://sport.mos.ru/',
  },
]
</script>

<template>
  <main class="placeholder">
    <div class="placeholder__container">
      <div class="placeholder__event">
        <div class="placeholder__date">
          <span class="placeholder__day">19</span>
          <span class="placeholder__date-copy">
            <span class="placeholder__month">декабря</span>
            <span class="placeholder__year">2026 года</span>
          </span>
        </div>

        <p class="placeholder__venue">Лужники,<br class="placeholder__venue-break" /> Южный спортивный центр</p>

        <div class="placeholder__identity">
          <Image
            class="placeholder__event-logo"
            src="/images/hero/logo.webp"
            alt="День хоккея"
            width="870"
            height="665"
            loading="eager"
            fetchpriority="high"
          />
          <p class="placeholder__participation">Участие<br />бесплатное</p>
        </div>
      </div>

      <div class="placeholder__right">
        <div class="placeholder__partners" aria-label="Организаторы и партнёры">
          <a
            v-for="partner in partners"
            :key="partner.src"
            class="placeholder__partner-link"
            :href="partner.href"
            target="_blank"
            rel="noopener noreferrer"
          >
            <Image
              class="placeholder__partner"
              :src="partner.src"
              :alt="partner.alt"
              :width="partner.width"
              height="42"
              loading="eager"
            />
          </a>
        </div>

        <div class="placeholder__copy">
          <p class="placeholder__description">
            Скоро на сайте появится больше информации, расписание и подробности по всем активностям.
            Следите за обновлениями — будет интересно!
          </p>

          <p class="placeholder__notice">
            С другими событиями вы можете<br /> ознакомиться на портале
            <a href="https://sport.mos.ru/" target="_blank" rel="noopener noreferrer">Московского спорта</a>
          </p>
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss">
.placeholder {
  width: 100%;
  min-height: 100%;
  padding: 4rem 0;
  display: flex;
  align-items: center;
  color: $white;
  background-color: #090C3D;
  background-image:
    linear-gradient(0deg, rgba(9, 12, 61, 0.9) 0%, rgba(9, 12, 61, 0.9) 100%),
    linear-gradient(180deg, rgba($navy-950, 0.9) 0%, rgba($navy-950, 0) 90%),
    url('/images/hero/hero-bg.webp'),
    url('/images/hero/hero-bg.webp');
  background-repeat: no-repeat;
  background-position: center, center, center top, center top;
  background-size: 100% 100%, 100% 100%, cover, cover;
  background-blend-mode: color-dodge, normal, normal, normal;

  @media (max-width: $tablet) {
    padding: 5rem 0 3.4rem;
    align-items: flex-start;
    background-color: $darkBlue;
    background-image: url('/images/hero/hero-bg-mob.webp');
    background-position: bottom;
    background-size: cover;
    background-blend-mode: normal;
  }

  &__container {
    width: calc(100% - 4rem);
    max-width: 120rem;
    margin: auto;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;

    @media (max-width: $tablet) {
      margin: 0 auto;
      display: grid;
      grid-template-columns: minmax(0, 1fr);
    }
  }

  &__event {
    width: 58rem;
    position: relative;
    flex: 0 0 auto;

    @media (max-width: $tablet) {
      width: 100%;
      display: flex;
      flex-direction: column;
      order: 2;
    }
  }

  &__date {
    position: absolute;
    top: -0.7rem;
    left: 0;
    z-index: 1;
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    font-family: $xmind;
    font-style: italic;
    font-weight: 700;
    text-transform: uppercase;

    @media (max-width: $tablet) {
      position: static;
      margin-top: 1.9rem;
      order: 2;
      gap: 0.9rem;
    }
  }

  &__day {
    font-size: 6rem;
    line-height: 95%;

    @media (max-width: $tablet) {
      font-size: 5.4273rem;
    }
  }

  &__date-copy {
    padding-top: 0.4rem;
    display: flex;
    flex-direction: column;

    @media (max-width: $tablet) {
      padding-top: 0.3rem;
    }
  }

  &__month {
    font-size: 2.8rem;
    line-height: 100%;

    @media (max-width: $tablet) {
      font-size: 2.5327rem;
    }
  }

  &__year {
    margin-top: 0.2rem;
    font-size: 1.6rem;
    line-height: 100%;

    @media (max-width: $tablet) {
      font-size: 1.4473rem;
    }
  }

  &__venue {
    width: 22rem;
    margin: 5.8rem 0 0;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
    font-family: $finlandica;
    font-size: 1.4rem;
    font-style: normal;
    font-weight: 500;
    line-height: 130%;

    @media (max-width: $tablet) {
      width: 100%;
      margin: 0.5rem 0 0;
      position: static;
      order: 3;
    }
  }

  &__venue-break {
    display: initial;

    @media (max-width: $tablet) {
      display: none;
    }
  }

  &__identity {
    width: 100%;
    top: 0.5rem;
    position: relative;

    @media (max-width: $tablet) {
      max-width: 58rem;
      top: 0;
      align-self: center;
      order: 1;
    }

    @media (max-width: $mobile) {
      max-width: none;
    }
  }

  &__event-logo {
    width: 100%;
    height: auto;
  }

  &__participation {
    margin: 0;
    position: absolute;
    right: 5.2rem;
    bottom: 0.4rem;
    font-family: $xmind;
    font-size: 2rem;
    font-style: italic;
    font-weight: 800;
    line-height: 110%;
    text-transform: uppercase;

    @media (max-width: $tablet) {
      right: 0.1rem;
      bottom: 0.3rem;
      font-size: 1.6454rem;
    }
  }

  &__right {
    width: 55.3rem;
    flex: 0 0 auto;

    @media (max-width: $tablet) {
      width: auto;
      display: contents;
    }
  }

  &__partners {
    height: 4.2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;

    @media (max-width: $tablet) {
      margin-bottom: 4.1rem;
      order: 1;
    }

    @media (max-width: $mobile) {
      height: 2.4rem;
    }
  }

  &__partner-link {
    height: 4.2rem;
    display: flex;
    align-items: center;
    opacity: 1;
    transition: opacity 200ms ease, transform 200ms ease;

    &:hover {
      opacity: 0.72;
      transform: translateY(-0.2rem);
    }

    &:focus-visible {
      outline: 0.2rem solid $white;
      outline-offset: 0.4rem;
    }

    @media (max-width: $mobile) {
      height: 2.4rem;
    }
  }

  &__partner {
    width: auto;
    height: 4.2rem;

    @media (max-width: $mobile) {
      height: 2.4rem;
    }
  }

  &__copy {
    margin-top: 8.3rem;

    @media (max-width: $tablet) {
      max-width: 55.3rem;
      margin-top: 3.3rem;
      order: 3;
    }
  }

  &__description {
    margin: 0;
    font-family: $finlandica;
    font-size: 2rem;
    font-style: normal;
    font-weight: 500;
    line-height: 120%;

    @media (max-width: $tablet) {
      font-size: 1.6rem;
    }
  }

  &__notice {
    margin: 3rem 0 0;
    padding: 2rem 2.4rem 3.2rem;
    border-radius: 12px;
    background: $red-900;
    font-family: $finlandica;
    font-size: 2rem;
    font-style: normal;
    font-weight: 500;
    line-height: 120%;

    @media (max-width: $tablet) {
      font-size: 1.6rem;
    }
  }

  &__notice a {
    color: inherit;
    text-decoration: underline;
    text-decoration-thickness: 0.1rem;
    text-underline-offset: 0.2rem;
  }
}
</style>
