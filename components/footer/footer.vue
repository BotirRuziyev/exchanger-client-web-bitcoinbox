<template>
  <footer class="footer">
    <div class="footer-in">
      <div class="footer-left__block">
        <div class="logo">
          <nuxt-link to="/">
            <img src="~assets/img/logo.svg" alt="" />
          </nuxt-link>
        </div>
        <div class="cryptocurrency-exchange">
          Лучшая платформа для обмена криптовалют.
        </div>
        <div class="reserved">© 2025 BitcoinBox | All rights reserved</div>
        <div class="telegram-link">
          <a href="#">
            <img src="~assets/img/icons/telegram.svg" alt="" />
          </a>
        </div>
      </div>
      <nav class="footer-nav">
        <div class="footer-nav__item">
          <div class="head">Компания</div>
          <ul class="nav-link__list">
            <li class="list-item">
              <a href="" class="nav-link"> Обмен </a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">Инструкции</a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">О нас </a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">Контакты </a>
            </li>
          </ul>
        </div>
        <div class="footer-nav__item">
          <div class="head">Платформа</div>
          <ul class="nav-link__list">
            <li class="list-item">
              <a href="" class="nav-link"> Обзор </a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">Карта</a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">Изменения</a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">Блог </a>
            </li>
          </ul>
        </div>
        <div class="footer-nav__item">
          <div class="head">Ресурсы</div>
          <ul class="nav-link__list">
            <li class="list-item">
              <a href="" class="nav-link"> Документация </a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">FAQ</a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">Условия пользования</a>
            </li>
            <li class="list-item">
              <a href="" class="nav-link">Политика конфиденциальности </a>
            </li>
          </ul>
        </div>
      </nav>
      <div class="footer-support">
        <div class="head">Поддержка</div>
        <div class="support-item">
          <div class="label">Email</div>
          <a href="mailto:support@bitcoinbox.com" class="email-link">
            support@bitcoinbox.com
          </a>
        </div>
        <div class="support-item">
          <div class="label">Время работы</div>
          <div class="working-hours">Пн-Вс с 10:00 до 22:00 (Киев)</div>
          <div class="working-hours__about">
            (в случае возникновения вопросов в нерабочее время, вопросы и заявки
            будут проработаны на следующий день.)
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
