<script setup lang="ts">
import { toggleDark } from '~/composables/dark'

const { t, availableLocales, locale } = useI18n()

function toggleLocales() {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}
</script>

<template>
  <nav class="icon-color mt-6 flex items-center justify-center gap-4 text-2xl opacity-75">
    <RouterLink class="hover:text-teal-600" to="/" :title="t('button.home')">
      <div class="i-carbon-campsite" />
    </RouterLink>

    <button class="hover:text-teal-600" :title="t('button.toggle_dark')" @click="toggleDark()">
      <div class="i-carbon-sun dark:i-carbon-moon" />
    </button>

    <button class="hover:text-teal-600" :title="t('button.toggle_langs')" @click="toggleLocales()">
      <div class="i-carbon-language" />
    </button>

    <RouterLink class="hover:text-teal-600" to="/about" :title="t('button.about')">
      <div class="i-carbon-dicom-overlay" />
    </RouterLink>

    <a rel="noreferrer" href="https://github.com/zguolee/starter-vue" target="_blank" title="GitHub">
      <div class="i-carbon-logo-github" />
    </a>
  </nav>
</template>
