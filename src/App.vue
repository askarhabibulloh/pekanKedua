<script setup lang="ts"></script>

<template>
  <div class="flex flex-col container mx-auto p-4 gap-10">
    <!-- Header -->
    <div class="flex justify-between p-4">
      <!-- Menu -->
      <div>
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
      </div>
      <!-- Auth User -->
      <div>
        <p v-if="false">John Doe</p>
        <div>
          <router-link to="/">Login</router-link>
        </div>
      </div>
    </div>
    <!-- Body -->
    <router-view></router-view>
  </div>
</template>
