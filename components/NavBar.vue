<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'

// const { session } = useAuth();
const navTransform = ref('translateY(0)')

let lastScrollPosition = 0

const route = useRoute()
route.path

function handleScroll() {
  const scrollY = window.scrollY
  navTransform.value
    = scrollY > lastScrollPosition ? 'translateY(-100%)' : 'translateY(0)'
  lastScrollPosition = scrollY
}

function handleIndicator(el: HTMLElement) {
  const indicator = document.querySelector('.nav-indicator') as HTMLElement
  const items = document.querySelectorAll('.nav-item')

  items.forEach((item) => {
    item.classList.remove('is-active')
    item.removeAttribute('style')
  })

  indicator.style.width = `${el.offsetWidth}px`
  indicator.style.left = `${el.offsetLeft}px`

  const activeColor = el.getAttribute('active-color')
  if (activeColor !== null) {
    indicator.style.backgroundColor = activeColor
    el.style.color = activeColor
  }

  el.classList.add('is-active')
}

interface HTMLElementWithActiveClass extends HTMLElement {
  classList: DOMTokenList & {
    contains(token: string): boolean
  }
}
// Function to setup listeners
function setupIndicatorListeners() {
  const items: NodeListOf<HTMLElement> = document.querySelectorAll('.nav-item')
  const indicator: HTMLElement | null
    = document.querySelector('.nav-indicator')

  items.forEach((item: HTMLElement) => {
    if (item.getAttribute('href') === route.path) {
      item.classList.add('is-active')
      handleIndicator(item)
    }
    item.addEventListener('click', e =>
      handleIndicator(e.target as HTMLElement))
    if ((item as HTMLElementWithActiveClass).classList.contains('is-active'))
      handleIndicator(item)
  })
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  setupIndicatorListeners()
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})


const navItems = [
  { label: 'Home', href: '/' },
  { label: 'About', href: '/about' },
  { label: 'Contact', href: '/contact' },
]


const isOpen = ref(false)



</script>

<template>
  <div
    ref="nav"
    class="fixed top-0 z-50 flex w-full items-center lg:justify-around gap-4 lg:gap-0 bg-white p-2 text-gray-900 shadow-md transition-transform duration-300 ease-in-out"
    :style="{ transform: navTransform }"
  >
   <Button class="bg-transparent lg:hidden block" label="Open" @click="isOpen = true" >
        <Icon name="solar:hamburger-menu-linear" class="text-6xl" />
       </Button>
    <div class="flex w-fit items-center space-x-3">
      <Icon name="skill-icons:nuxtjs-dark" class="text-5xl" />
    
    </div>
    <div class="relative hidden w-fit overflow-hidden lg:inline-flex">
      <NuxtLink href="/" class="nav-item is-active" active-color="orange">
        Home
      </NuxtLink>
      <NuxtLink href="/about" class="nav-item" active-color="orange">
        About
      </NuxtLink>
      <NuxtLink href="/contact" class="nav-item" active-color="orange">
        Contact
      </NuxtLink>
      <span class="nav-indicator" />
    </div>
    <div class="flex items-center justify-center space-x-4">
   
    
      <a class="hidden lg:block " href="https://github.com/TungLe0319">
        <Icon name="skill-icons:github-dark" class="text-3xl" />
      </a>
    </div>

      <USlideover v-model="isOpen" :ui="{
        background:'bg-white dark:bg-white',
      }">
        <div class="p-4  ">
        <ul class="space-y-6   ">
          <li   v-for="navItem in navItems" class="hover:brightness-50 text-6xl flex items-center justify-start font-bold ">
            <NuxtLink  :href="navItem.href" class="nav-item is-active" active-color="orange">
             {{  navItem.label }}
            </NuxtLink>
          </li>
        
        </ul>

        </div>
      </USlideover>
  </div>
</template>

<style scoped>
.nav-item {
  padding: 20px;
  transition: 0.3s;
  margin: 0 6px;
  z-index: 1;
 
  position: relative;
}

.nav-item:before {
  content: "";
  position: absolute;
  bottom: -6px;
  left: 0;
  width: 100%;
  height: 5px;
  background-color: #dfe2ea;
  border-radius: 8px 8px 0 0;
  opacity: 0;
  transition: 0.3s;
}

.nav-item:not(.is-active):hover:before {
  opacity: 1;
  bottom: 0;
}

.nav-indicator {
  position: absolute;
  left: 0;
  bottom: 0;
  height: 4px;
  transition: 0.4s;
  height: 5px;
  z-index: 1;
  border-radius: 8px 8px 0 0;
}

@media (max-width: 580px) {
  .nav {
    overflow: auto;
  }
}
</style>
