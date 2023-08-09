<template>
    <div>
        You need be verfied first to see this page!
    </div>
    <Link method="post" as="button" class="text-sky-600 dark:text-sky-400 "
    :href="route('verification.send')"> 
    Resend verification email
    </Link>
  </template>

 
  
  <script setup>
import { Link } from '@inertiajs/inertia-vue3';

  
  </script>
  
