
import { SlotFlags } from '@vue/shared';

<template>
  <div class="flex flex-col h-screen">
    <!-- Menubar -->
    <Menubar :menuItems="[
      { name: 'Home', href: '/' },
      { name: 'About', href: '/about' },
    ]" />
    <!-- Content area -->
    <div class="flex flex-1">
      <!-- Sidebar -->
      <Sidebar />
      <!-- Main content -->
      <main class="flex-1 p-6">
        <slot />
      </main>
    </div>
  </div>
</template>


