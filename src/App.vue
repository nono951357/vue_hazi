<template>
    <div class="font-sans bg-background-color min-h-screen">
      <nav class=" text-white p-4 flex justify-between items-center shadow-md">
        <router-link to="/" class="text-xl font-bold">EcoVision Solutions</router-link>
        <div>
          <router-link to="/" class="px-4 hover:underline">Főoldal</router-link>
          <router-link to="/about" class="px-4 hover:underline">Rólunk</router-link>
        </div>
      </nav>
      <router-view></router-view>
    </div>
  </template>