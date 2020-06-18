<template>
  <div class="wrapper">
    <header class="header">
      <a href="https://stankin.ru" class="blue-wrapper stankin-button" target="_blank">На сайт "Станкин"</a>
      <img class="logo-vipusknoi" src="./assets/logo.svg" />
      <h1 class="header_title">
        всероссийский студенческий выпускной
      </h1>
      <p class="header_date">27 июня 2020</p>
      <p class="header_text">Выпускной начнётся через</p>
      <Timer dateTime="2020-06-27 12:00:00" />
    </header>
    <main class="main">
      <h2 class="main_title">Праздник, который соберет всех</h2>
      <div class="main_text-block">
        Не пропусти грандиозное событие российского интернета! Всероссийский студенческий выпускной из всех университетов страны!<br /><br />
        Все вместе - от студентов до глав корпораций! В эфире вас будут ждать поздравления от Министра науки и высшего образования, генерального директора АНО «Россия – страна возможностей» и Союза ректоров, а также лучшие творческие номера от выпускников. В программе выступления молодых и известных музыкантов и артистов, любимые песни, конкурсы и подарки.<br /><br />
        Станьте зрителем первого в истории Всероссийского онлайн-выпускного для студентов!
      </div>
      <h2 class="main_title">Лучшие выпускники «Станкин»</h2>
      <div class="best-students-block-wrapper">
        <BestStudents v-for="(studentsGroup, i) in students"
                      :key="i"
                      :title="i"
                      :students="studentsGroup" />
      </div>
      <h2 class="main_title">Партнеры мероприятия</h2>
      <div class="main_partners-block">
        <a href="https://rsv.ru/main/RMain" target="_blank" class="main_partners-block-link">
          <img src="./assets/partner-1.png" class="main_partners-block-img" />
        </a>
        <a href="https://www.minobrnauki.gov.ru/" target="_blank" class="main_partners-block-link">
          <img src="./assets/partner-2.png" class="main_partners-block-img" />
        </a>
        <a href="https://www.rsr-online.ru/" target="_blank" class="main_partners-block-link">
          <img src="./assets/partner-3.png" class="main_partners-block-img" />
        </a>
      </div>
    </main>
    <footer class="footer">
      <img class="footer_organisator" src="./assets/eagle.png" />
      <div class="footer_links">
        <a href="https://www.instagram.com/minobrnauki_russia/" target="_blank" class="footer_links-item footer_links-item-instagram" />
        <a href="https://facebook.com/minobrnaukigov/" target="_blank" class="footer_links-item footer_links-item-facebook" />
        <a href="https://vk.com/minobrnauki" target="_blank" class="footer_links-item footer_links-item-vk" />
        <a href="https://vk.com/minobrnauki" target="_blank" class="footer_links-item footer_links-item-site" />
      </div>
    </footer>
  </div>
</template>

<script>
import Timer from './components/timer/'
import BestStudents from './components/best-students/'

export default {
  name: 'App',
  components: {
    Timer,
    BestStudents
  },
  data () {
    return {
      students: {
        'Наука' : [
          'Гриднев Михаил Александрович',
          'Малахинский Александр Петрович',
          'Лапин Борис Сергеевич'
        ],
        'Образование' : [
          'Чиркова Виктория Олеговна',
          'Яскевич Константин Игоревич',
          'Семеняка  Алина Геннадиевна'
        ],
        'Общественная деятельность' : [
          'Вельничерь Юлия Юрьевна',
          'Фирфаров Алексей Сергеевич',
          'Журавлева Мария Андреевна'
        ],
        'Преподавание' : [
          'Пушков Роман Львович',
          'Сосенушкин Сергей Евгеньевич',
          'Можаровская Алевтина Александровна'
        ]
      }
    }
  }
}
</script>

