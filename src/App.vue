<!-- eslint-disable vue/no-template-shadow -->
<script setup>
import { ref } from 'vue'
import resume from '@/resume.json'

const myResume = ref(resume)

</script>

<template>
  <header>
    <nav>
      <span class='nav-title'>
        YangReZhe's resume
      </span>
    </nav>
  </header>
  <main>
    <section class='personal-info'>
      <div class='avatar'>
        <img
          alt=''
          class='avatar-img'
          src='./photo.jpg'
        >
      </div>
      <h1 class='name'>
        楊睿哲
      </h1>
      <div class='social-media'>
        <a
          href='https://www.facebook.com/yang.rui.zhe.68283/?locale=zh_TW'
          target='_blank'
        >
          <i class='fa-brands fa-facebook fa-lg' />
        </a>
        <a
          href='https://www.instagram.com/yang_rui_zhe0418/'
          target='_blank'
        >
          <i class='fa-brands fa-instagram fa-lg' />
        </a>
        <a href='https://mail.google.com/mail/u/0/#inbox'>
          <i class='fa-regular fa-envelope fa-lg' />
        </a>
      </div>
      <div class='title'>
        反應靈敏 | 積極認真 | 勇於學習
      </div>
      <div class='description'>
        您好，我是楊睿哲，我樂於接受挑戰，喜歡接觸不同領域的事物，以累積多元的工作經驗、技能與知識，藉此鍛鍊自己，提升在各種環境與領域中的適應能力。
        <br>
        在過往工作經驗中，在服務業與企劃領域，累積溝通協調與問題排除能力，能在不同情境下快速理解需求並提出解決方案。
        <br>
        為實現轉職目標，參加勞動部勞動力發展署職業訓練，並同時學習 HTML、CSS、JavaScript、Vue 框架以及 Git 版本控制。期許將過去累積的使用者思維與執行能力帶入前端領域，成為能獨當一面的前端工程師。
      </div>
    </section>
    <section class='skill-section'>
      <h2>專業技能</h2>
      <div class='skills'>
        <div
          v-for='resume in myResume.ProfessionalSkill'
          :key='resume.SkillName'
          class='skill'
        >
          <h3
            class='skill-name'
          >
            {{ resume.SkillName }}
          </h3>
          <p
            class='skill-description'
          >
            {{ resume.Description }}
          </p>
        </div>
      </div>
    </section>

    <section class='aboutSchool'>
      <h2>學歷</h2>
      <hr>
      <div class='Educational'>
        <div
          v-for='school in myResume.Education'
          :key='school.SchoolName'
          class='qualifications'
        >
          <h3>{{ school.SchoolName }}</h3>
          <ul>
            <li>{{ school.Department }}</li>
          </ul>
        </div>
      </div>
    </section>

    <section class='Certificate'>
      <div class='Certificates'>
        <h2>證照</h2>
        <hr>
        <div
          v-for='Certification in myResume.Certifications'
          :key='Certification.CertificationsName'
          class='Certification'
        >
          <ul>
            <li>{{ Certification.CertificationsName }}</li>
          </ul>
        </div>
      </div>
    </section>

    <section class='experience-section'>
      <h2>工作經歷</h2>
      <hr>
      <div class='experience'>
        <div
          v-for='resume in myResume.WorkExperience'
          :key='resume.jobTitle'
          class='experience-item'
        >
          <h3 class='job-title'>
            {{ resume.jobTitle }}
          </h3>
          <span class='company'><i class='fa-regular fa-building' />{{ resume.company }}</span>
          <span class='duration'><i class='fa-regular fa-calendar-days' />{{ resume.duration }}</span>
          <ul>
            <li
              v-for='responsibilities in resume.responsibilities'
              :key='responsibilities'
            >
              {{ responsibilities }}
            </li>
          </ul>
        </div>
        <hr>
      </div>
    </section>
  </main>
</template>

<style scoped>
html,
body {
  font-family: "Lato", "Noto Sans TC", sans-serif;
  margin: 0;
  padding: 0;
  color: #333333;
  background-color: #f6f7f8;
}

/* Here is header */
header {
  height: 60px;
  color: #666666;
  box-shadow: 0 4px 12px 0 rgba(0, 0, 0, 0.08);
}
nav {
  max-width: 820px;
  margin: 0 auto;
  height: 100%;
  padding: 0 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.nav-title {
  letter-spacing: 1px;
  font-weight: bold;
}
.nav-link {
  color: #666666;
}
/* Here is main */
main {
  max-width: 780px;
  margin: 0 auto;
  padding: 40px 20px;
}
h2 {
  font-size: 26px;
  margin: 24px 0 8px;
}
h3 {
  font-size: 21px;
  margin: 0 0 8px;
  font-weight: 500;
}
p {
  color: #666666;
}
section {
  margin-bottom: 48px;
}

/* Personal info */
.avatar {
  text-align: center;
}
.avatar-img {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
}
.name {
  text-align: center;
  font-size: 32px;
  margin: 20px 0;
}
.social-media {
  text-align: center;
  margin-bottom: 20px;
  font-size: 18px;
}
.social-media a {
  color: #999999;
  text-decoration: none;
  margin: 0 5px;
}
.social-media a:hover {
  color: #ff6600;
}
.title {
  margin-bottom: 20px;
  text-align: center;
  font-size: 14px;
  letter-spacing: 2px;
  color: #ff6600;
}

/* Skill */
.skills {
  display: flex;
  justify-content: space-between;
}
.skill {
  width: 30%;
  text-align: center;
}
.skill-name {
  border-top: 1px solid #999999;
  padding-top: 16px;
}

/* Experience */
hr {
  border: 0px;
  height: 1px;
  background: #cccccc;
  margin: 20px 0;
}

.experience-section hr:last-of-type {
  display: none;
}

.company,
.duration {
  margin-right: 20px;
  color: #666666;
  font-size: 12px;
}
.fa-building,
.fa-calendar-days {
  margin-right: 5px;
}

@media(max-width: 1399px){
  body{
    font-size: 16px;
  }
}

@media(max-width: 1023px){
  body{
    font-size: 15px;
  }
  main{
    padding: 32px 16px;
  }
  .skills {
    flex-wrap: wrap;
    gap: 16px;
    justify-content: center;
    grid-template-columns: repeat(2, 1fr);
  }
  .skill {
    width: calc(50% - 16px);
  }
}

@media(max-width: 752px){
  body{
    font-size: 14px;
  }
  main{
    padding: 24px 36px;
  }
  .skill {
    width: 100%;
  }
}
</style>
