<template>
  <NuxtLayout name="ottg">
    <NuxtPage />
  </NuxtLayout>
</template>
<script setup>
  useHead({
        htmlAttrs: {
            lang: 'en'
        },

        meta: [
            {
            hid: 'description',
            name: 'description',
            content: 'One-Trip-To-Go'
            }
        ],
        link: [
            {
            rel: 'icon',
            type: 'image/x-icon',
            href: '/favicon.ico'
            }
        ],

        script: [
            {
            src: 'https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.min.js',
            ssr: true
            }
        ]
    })

</script>
<style>
    @import 'bootstrap/dist/css/bootstrap.css';
    @import '~/css/index.css';
    @import '~/css/activities.css';
    @import '~/css/hotels.css';
</style>
