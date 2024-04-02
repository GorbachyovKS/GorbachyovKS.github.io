<template>
    <div class="project" ref="projectItem">
        <h2 class="project__title">{{ project.title }}</h2>
        <div class="project-main">
            <div class="project-description">{{ project.subtitle }}</div>
            <div class="project-technologies">
                <span>Технологии: </span>
                <ul>
                    <li v-for="(technology, index) in project.technologies" :key="index">{{ technology }}</li>
                </ul>
            </div>
            <div class="project-link" v-if="project.link">
                <span>Website: </span>
                <button class="button" @mouseleave="handlerMouseleave" @mousemove="handlerMousemove">
                    <a target="_blank" :href="project.link">{{ project.title }}</a>
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
import { onMounted, onUnmounted, ref, toRefs } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

const props = defineProps({
    project: Object,
    projects: Object
})

const {project, projects} = toRefs(props)



const handlerMousemove = (e) => {
    if (!e.target.classList.contains('button')) return
    const xTo = gsap.quickTo(e.target, 'x', {
        duration: 1,
        ease: 'elastic.out(1, 0.3)'
    })
    const yTo = gsap.quickTo(e.target, 'y', {
        duration: 1,
        ease: 'elastic.out(1, 0.3)'
    })
    
    const { clientX, clientY } = e
    const { height, width, left, top } = e.target.getBoundingClientRect()
    const x = clientX - (left + width / 2)
    const y = clientY - (top + height / 2)

    xTo(x)
    yTo(y)
}

const handlerMouseleave = (e) => {
    if (!e.target.classList.contains('button')) return
    const xTo = gsap.quickTo(e.target, 'x', {
        duration: 1,
        ease: 'elastic.out(1, 0.3)'
    })
    const yTo = gsap.quickTo(e.target, 'y', {
        duration: 1,
        ease: 'elastic.out(1, 0.3)'
    })
    
    xTo(0)
    yTo(0)
}

const projectItem = ref();

onMounted(() => {
      gsap.from(projectItem.value, {
        scrollTrigger: {
          scroller: '.wrapper',
          trigger: projectItem.value,
          toggleActions:'restart none none none',
        },
        x: 500,
        duration: 0.5,
      });
    });

</script>

<style scoped>
.project {
    display: flex;
    flex-direction: column;
    border-radius: 5px;
    background: rgba(255, 255, 255, 0.25);
    padding-bottom: 15px;
}

.project__title {
    padding: 10px;
}
.project-main {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
.project-photo {
}

.project-photo img {
    width: 100%;
    height: auto;
}
.project-description {
    padding: 0 10px;

}
.project-technologies,
.project-technologies ul {
    display: flex;
    gap: 7.5px;
    padding: 0 10px; 
}

.project-technologies ul {
    flex-wrap: wrap;

}

.project-technologies ul li {
    display: flex;
    gap: 7.5px;
}

.project-technologies ul li::after {
    content: '/';
    color: black;
    display: block;
}

.project-technologies ul li:last-child::after {
    content: unset;
}

.project-link {
    padding: 0 10px 0px ;
    display: flex;
    align-items: center;
    gap: 10px

}

button {
    padding: 5px 15px;
    border-radius: 5px;
    background: black;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 30px;
}

button a {
    font-weight: bolder;
    color: white;
    line-height: 0;
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
}


</style>