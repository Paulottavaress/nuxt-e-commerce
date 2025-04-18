<template>
  <div class='flex flex-col min-h-screen'>
    <app-header />
    <UContainer class='flex-1'>
      <slot />
    </UContainer>
    <app-footer />
  </div>
</template>
