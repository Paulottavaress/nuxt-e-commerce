<script setup lang='ts'>
import type { NavigationMenuItem } from '@nuxt/ui'
import { breakpointsTailwind, useBreakpoints } from '@vueuse/core'

const breakpoints = useBreakpoints(breakpointsTailwind)
const smallerThanLg = breakpoints.smaller('lg')
const navItemsDesktop: NavigationMenuItem[] = [
  {
    label: 'Products List',
    icon: 'i-lucide-shopping-bag',
    to: '/'
  },
  {
    label: 'Cart',
    icon: 'lucide-shopping-basket',
    to: '/cart',
    badge: '€100.00 (2)'
  }
]
const navItemsMobile: NavigationMenuItem[][] = [
  [
    {
      label: '',
      icon: 'i-lucide-menu',
      active: true,
      children: [...navItemsDesktop]
    }
  ]
]
const navItems = ref<NavigationMenuItem[][]>([[]])
const navOrientation = ref('horizontal')

const configureNavDisplay = () => {
  if (smallerThanLg.value) {
    navItems.value = navItemsMobile
    navOrientation.value = 'vertical'
  } else {
    navItems.value = navItemsDesktop
    navOrientation.value = 'horizontal'
  }
}

onMounted(() => {
  configureNavDisplay()
})

watch(smallerThanLg, () => {
  configureNavDisplay()
})
</script>

<template>
  <header class='bg-black'>
    <UContainer class='flex lg:flex-row-reverse justify-between items-center py-2'>      
      <UNavigationMenu
        :orientation='navOrientation'
        :items='navItems'
        class='w-fit-content lg:w-auto'
      />
      <div>
        <NuxtLink to='/'>
          <NuxtImg
            src='/img/logo.png'
            alt='Nuxt E-Commerce Logo'
            sizes='100vw 48px'
          />
        </NuxtLink>
      </div>
    </UContainer>
  </header>
</template>