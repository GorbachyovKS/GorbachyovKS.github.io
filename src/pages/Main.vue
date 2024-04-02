<template>
    <div class="page">
        <header class="header">
            <div class="header-logo logo">{{ `<GKS>` }}</div>
            <nav class="header-nav">
                <ul>
                    <li>
                        <a href="#about">Обо мне</a>
                    </li>
                    <li>
                        <a href="#projects">Проекты</a>
                    </li>
                    <li>
                        <a @click="scrollBottom">Контакты</a>
                    </li>
                </ul>
            </nav>
        </header>
        <main>
            <a name="about"></a>
            <section class="about">
                <div class="about-wrapper">
                    <div class="about-text">
                        <h1>Обо мне</h1>
                        <div>
                            <p>
                                <ul>
                                    <li>📍 Превращаю абстрактные идеи в удобный UI</li>
                                    <li>📍 Проявляю внимание к деталям и мелочам</li>
                                    <li>📍 Пишу простой поддерживаемый код</li>
                                    <li>📍 Имею отличные навыки коммуникации</li>
                                </ul>
                            </p>
                            <p>
                                Для меня веб-разработка – это не только работа, но и хобби,
                                которое вдохновляет и побуждает меня постоянно
                                совершенствовать свои навыки и следить за последними
                                тенденциями в мире веба.
                            </p>
                            <p>
                                Я открыт к новым вызовам и готов к работе в динамичной и
                                творческой среде, где я мог бы внести свой вклад и расти
                                профессионально.
                            </p>
                        </div>
                    </div>
                    <div class="about-img">
                        <div class="about-img__container">
                            <img :src="My_photo" alt="my-photo">
                        </div>
                    </div>
                </div>
                <div class="about-achivements">
                    <h3>Достижения</h3>
                    <div>
                        <ul>
                            <li>— Реализовал backend- и frontend-часть сервиса, который ищет
                            утечки воды в системе водоснабжения Минска. Проект успешно
                            внедрен компанией и пользуется спросом по сей день</li>
                            <li>— Разработал frontend-часть сервиса автоматизированного
                            управления очистными сооружениями, который внедрен в
                            нескольких городах Беларуси</li>
                            <li>— Разработал корпоративный сайт для компании с нуля, начиная
                            с концепции, заканчивая деплоем и поддержкой</li>
                            <li>— Несколько успешно завершенных заказов на фрилансе</li>
                            <li>— Многочисленные pet-проекты</li>
                        </ul>
                    </div>
                </div>
                <div class="about-technologies">
                    <h3>Стек технологий</h3>
                    <div>
                        <ul>
                            <li>Языки программирования: JavaScript, TypeScript, SQL</li>
                            <li>Фреймворки: React, Vue и их экосистеми, Next.js, Nuxt.js для SSR</li>
                            <li>Библиотеки: 
                                <br>state-management: RTK, Zustand, Recoil, Vuex, Pinia
                                <br>UI: AntDesign, MaterialUI, Element Plus
                                <br>Остальное: Chart.js, Socket.io, GSAP, Pixi, Three,js, Axios</li>
                            <li></li>
                            <li></li>
                        </ul>
                    </div>
                </div>
            </section>
            <a name="projects"></a>
            <section class="projects" ref="projectsItem">
                <h1>Проекты</h1>
                <Project :projects="projectsItem" v-for="project in projects" :key="project.title" :project="project"/>
            </section>
            <section class="contacts">
                <h1>Контакты</h1>
                <div class="text-links">
                    <div class="text-link">
                        <span>💻 Telegram:</span>
                        <span>
                            <a target="_blank" href="https://t.me/gorbachyovKS">gorbachyovKS</a>
                        </span>
                    </div>
                    <div class="text-link">
                        <span>✉️ Почта:</span>
                        <span>
                            <a target="_blank" href="mailto:gorbachyovKS@gmail.com">gorbachyovKS@gmail.com</a>
                        </span>
                    </div>
                    <div class="text-link">
                        <span>📞 Мобильный телефон:</span>
                        <span>
                            <a target="_blank" href="tel:+375259398755">375 25 939 87 55</a>
                        </span>
                    </div>
                </div>                
                <div class="circle-links">
                    <ul>
                        <li><a target="_blank" href="https://rabota.by/resume/91e54660ff0cd21fc00039ed1f42656d753262?from=share_ios">
                            <i class="fa-solid fa-r"></i>
                        </a></li>
                        <li><a target="_blank" href="https://www.linkedin.com/authwall?trk=bf&trkInfo=AQFRae9HJYOvMQAAAY1krrYgEq8s7ASGc_WRYqOUgP5w0WOe_taSpZlhm1zklDOYrGfsRfMBnP4Uo-o8qmgFcxULvPcrdsl5QZAO0NrrIhzPTM6d-1ZVCV-HNkbzyEW-1UEIGt0=&original_referer=&sessionRedirect=https%3A%2F%2Fwww.linkedin.com%2Fin%2Fkirill-gorbachyov-08a15b2b2%3Futm_source%3Dshare%26utm_campaign%3Dshare_via%26utm_content%3Dprofile%26utm_medium%3Dios_app">
                            <i class="fa-brands fa-linkedin-in"></i>
                        </a></li>
                        <li><a href="https://www.fl.ru/users/gorbachyovks/portfolio/" target="_blank">
                            <i class="fa-solid fa-f"></i>
                            <i class="fa-solid fa-l"></i>
                        </a></li>
                    </ul>
                </div>
            </section>
        </main>
        <footer>
            <div class="footer-logo logo">{{ `</GKS>` }}</div>
        </footer>
    </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import Project from '@/components/Project.vue'
import My_photo from '@/assets/my_photo.webp'
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
import { SteppedEase } from 'gsap/gsap-core';
gsap.registerPlugin(ScrollTrigger);

const projectsItem = ref()

const scrollBottom = () => {
    const page = document.querySelector('.wrapper')
    page.scrollTo({
        bottom: 100,
        left: 0,
    })
}

onMounted(() => {
    const navList = document.querySelector('.header-nav').children[0].children
    
    gsap.from('.header', {
        y: -50,
        opacity: 0,
        duration: 1
    })

    let i = [...navList].forEach((item, index) => {
        gsap.from(item, {
            x: 50,
            opacity: 0,
            delay: 1 + index / 4,
            duration: 1
        })
    })

    gsap.from('.about-wrapper', {
        y: 50,
        opacity: 0,
        delay: 0.5,
        duration: 1
    })
    gsap.from('.about-achivements', {
        y: 50,
        opacity: 0,
        delay: 1,
        duration: 1
    })
    gsap.from('.about-technologies', {
        y: 50,
        opacity: 0,
        delay: 1.5,
        duration: 1
    })

    gsap.fromTo(".header-logo", 8, {
        width: "0",
        }, {
        width: "70px", /* same as CSS .line-1 width */
        ease: SteppedEase.config(5)
    }, 0);
    // text cursor animation
    gsap.fromTo(".header-logo", 0.5, {
        "border-right-color": "rgba(0,0,0,0.75)"
        }, {
        "border-right-color": "rgba(0,0,0,0)",
        repeat: -1,
        ease: SteppedEase.config(5)
    }, 0);
    gsap.fromTo(".footer-logo", 8, {
        width: "0",
        }, {
        width: "75px", /* same as CSS .line-1 width */
        ease: SteppedEase.config(6)
    }, 0);
    // text cursor animation
    gsap.fromTo(".footer-logo", 0.5, {
        "border-right-color": "rgba(0,0,0,0.75)"
        }, {
        "border-right-color": "rgba(0,0,0,0)",
        repeat: -1,
        ease: SteppedEase.config(6)
    }, 0);

})

const projects = ref([
    {
        title: 'Интернет-магазин', 
        subtitle: 'Интернет-магазин продуктов. С функцией фильтра с нумерацией страниц, поиском товаров, страницами каталога. Добавление товаров в избранное, корзину, заказы. Отдельная страница для каждого товара. Возможность поверхностной регистрации с хранилищем в localStorage, чтобы ходить по магазину как новый пользователь. Оценка продукта и многое другое. Заходите и попробуйте.', 
        technologies: ['React', 'Zustand', 'React-yandex-maps'],
        link: './projects/onlineStore/index.html', 
        img: 'online-store'
    },
    {
        title: 'Погода IOS', 
        subtitle: 'Приложение-клон погоды iOS. С функционалом как в оригинальном приложении. Просмотр погоды в реальном времени. Графики и другие метеорологические показетели', 
        technologies: ['Vue', 'Chart.js', 'Rest API', 'Pinia'],
        link: './projects/wheather/index.html', 
        img: 'weather'
    },
    {
        title: 'AMIS-LEAK', 
        subtitle: 'Коммерческое приложение AMIS-LEAK разработано компанией для частного использования. Получение данных с удаленного сервера для математических расчетов, использование данных для построения графиков и анализа. Создание собственных промежуточных точек на карте и полный доступ к их отключению/включению отслеживания. Интеграция с PostgreSQL для создания собственной базы данных, хранения необходимой информации и работы с ней.', 
        technologies: ['Vue', 'Pinia', 'CHart.js', 'Axios', 'Vue-yandex-maps', 'Xlsx',],
        link: '',
        img: 'amis-leak'
    },
])
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 50px;
    margin-bottom: 25px;
}

.logo {
    font-weight: bold;
    font-size: 20px;
    width: 70px;
}

.header-nav ul {
    display: flex;
    gap: 15px
}

.footer-logo,
.header-logo {
    width: 0px;
    border-right: 2px solid rgba(0,0,0,.75);
    text-align: center;
    white-space: nowrap;
    overflow: hidden;
}

.header-nav ul li {
    cursor: pointer;
}

.header-nav ul li  a::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 0.1em;
  background-color: rgb(0   0   0);
  opacity: 0;
  transition: opacity 300ms, transform 300ms;
}

.header-nav ul li a:hover::after,
.header-nav ul li a:focus::after {
  opacity: 1;
  transform: translate3d(0, 0.2em, 0);
}



.header-nav ul li a {
  overflow: hidden;
  display: block;
  position: relative;
  padding: 0.2em 0;
}

.header-nav ul li a::after {
  opacity: 1;
  transform: translate3d(-100%, 0, 0);
}

.header-nav ul li a:hover::after,
.header-nav ul li a:focus::after{
  transform: translate3d(0, 0, 0);
}

.page {
 padding: 10px 40px;
 max-width: 1512px;
 margin: 0 auto;
}

main {
    display: flex;
    flex-direction: column;
    gap: 50px;
    max-width: 800px;
    margin: 0 auto;
}

.about {
    display: flex;
    flex-direction: column;
    gap: 30px;
}
.about-wrapper {
    display: flex;
    gap: 10px;
    border-radius: 5px;
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(10px);

}
.about-text {
    display: flex;
    flex-direction: column;
    gap: 30px;
    padding: 5px;
    padding: 10px 15px;
}

.about-text > div {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 5px;
    flex: 1 0 0 ;
}
.about-img {
    width: 100%;
    
}
.about-img__container {
    min-width: 100px;
    line-height: 0;
    height: 100%;
    display: flex;
    align-items: center;
}

.about-img__container img {
    width: 100%;
    height: auto;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
}
.about-achivements {
    padding: 10px 15px;
    border-radius: 5px;
    background: rgba(255, 255, 255, 0.25);

}
.about-technologies {
    padding: 10px 15px;
    border-radius: 5px;
    background: rgba(255, 255, 255, 0.25);
}

.about-achivements h3,
.about-technologies h3 {
    margin-bottom: 10px;
}
.projects {
    display: flex;
    flex-direction: column;
    gap: 20px;
}
.contacts {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin-bottom: 40px;
}

.text-links {
    display: flex;
    flex-direction: column;
    gap: 5px;
}

.text-link {
    display: flex;
    align-items: center;
    min-width: fit-content;
}

.text-link span {
    display: flex;
    align-items: center
}

.text-link span a{
    display: flex;
    align-items: center;
}

.text-link span:first-child{
    width: 220px;
}
.circle-links ul{
    display: flex;
    gap: 15px;
}

.text-link  a::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 0.1em;
  background-color: rgb(0   0   0);
  opacity: 0;
  transition: opacity 300ms, transform 300ms;
}

.text-link a:hover::after,
.text-link a:focus::after {
  opacity: 1;
  transform: translate3d(0, 0.2em, 0);
}



.text-link a {
  overflow: hidden;
  display: block;
  position: relative;
  padding: 0.2em 0;
}

.text-link a::after {
  opacity: 1;
  transform: translate3d(-100%, 0, 0);
}

.text-link a:hover::after,
.text-link a:focus::after{
  transform: translate3d(0, 0, 0);
}

.circle-links li a{
    width: 50px;
    height: 50px;
    background: rgba(255, 255, 255, 0.25);
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    cursor: pointer;
    position: relative;
}

.circle-links li a:before {
  content: '';
  border-radius: 50%;
  position: absolute;
  bottom: 50%;
  left: 50%;
  transform: translate(-50%, 50%);
  width: 0%;
  height: 0%;
  transition: all .3s;
  z-index: -1;
}

.circle-links ul li:nth-of-type(1) a:hover:before {
    background: rgba(255, 0, 0, 0.5);
}

.circle-links ul li:nth-of-type(2) a:hover:before {
    background: rgba(10, 102, 194, 0.5);
}

.circle-links ul li:nth-of-type(3) a:hover:before {
    background: rgba(9, 255, 0, 0.5);
}

.circle-links a:hover:before  {
    height: 100%;
    width: 100%; 
}

@media screen and (max-width: 768px){
    * {
        font-size: 14px;
    }
    
    h1 {
        font-size: 20px;
    }

    h2 {
        font-size: 18px;
    }

    h3 {
        font-size: 16px;
    }

    a {
        font-size: 12px;
    }

    .page {
        padding: 10px 20px;
    }
}

@media screen and (max-width: 480px) {
    * {
        font-size: 12px;
    }
    
    h1 {
        font-size: 18px;
    }

    h2 {
        font-size: 16px;
    }

    h3 {
        font-size: 14px;
    }

    a {
        font-size: 10px;
    }

    .page {
        padding: 10px 10px;
    }

    .header-nav ul li a {
        font-size: 14px;
    }

    .text-link span,
    .text-link span a{
        font-size: 14px;
    }

    .circle-links *{
        font-size: 14px;
    }

    .about-text {
        gap: 15px;
    }

    .text-link {
        gap: 10px;
        justify-content: space-between;
    }

    .text-link span:first-child {
        width: unset;
    }
}

@media screen and (max-width: 400px)  {
    .about-img {
        display: none;
    }

    .text-link span,
    .text-link span a {
        font-size: 12px;
    }

    .header-nav ul li a {
        font-size: 13px;
    }
}
</style>