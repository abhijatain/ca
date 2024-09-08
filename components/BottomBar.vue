<template>
    <aside class="md:hidden fixed inset-x-0 bottom-0 z-10 flex w-full flex-row border-t bg-background sm:flex sm:w-auto p-3">
  <nav class="flex flex-row justify-around w-full items-center gap-4 px-2 sm:py-3">
    <a
      href="/"
      class="group flex h-9 w-9 shrink-0 items-center justify-center gap-2 rounded-full bg-primary text-lg font-semibold text-primary-foreground md:h-8 md:w-8 md:text-base"
    >
      <Package2 class="h-4 w-4 transition-all group-hover:scale-110" />
      <span class="sr-only">Acme Inc</span>
    </a>
    <TooltipProvider>
      <Tooltip>
        <TooltipTrigger as-child>
          <a
            href="/dashboard"
            class="flex h-9 w-9 items-center justify-center rounded-lg text-muted-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
          >
            <Home class="h-5 w-5" />
            <span class="sr-only">Dashboard</span>
          </a>
        </TooltipTrigger>
        <TooltipContent side="top">
          Dashboard
        </TooltipContent>
      </Tooltip>
    </TooltipProvider>
    <TooltipProvider>
      <Tooltip>
        <TooltipTrigger as-child>
          <a
            href="/course"
            class="flex h-9 w-9 items-center justify-center rounded-lg bg-accent text-accent-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
          >
            <BookOpenText class="h-5 w-5" />
            <span class="sr-only">Courses</span>
          </a>
        </TooltipTrigger>
        <TooltipContent side="top">
          Courses
        </TooltipContent>
      </Tooltip>
    </TooltipProvider>

    <TooltipProvider>
      <Tooltip>
        <TooltipTrigger as-child>
          <a
            href="/discussion"
            class="flex h-9 w-9 items-center justify-center rounded-lg text-muted-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
          >
            <MessageCircleCode class="h-5 w-5" />
            <span class="sr-only">Discussions</span>
          </a>
        </TooltipTrigger>
        <TooltipContent side="top">
          Discussions
        </TooltipContent>
      </Tooltip>
    </TooltipProvider>

    <DarkMode />

    <TooltipProvider>
      <Tooltip>
        <TooltipTrigger as-child>
          <a
            href="#"
            class="flex h-9 w-9 items-center justify-center rounded-lg text-muted-foreground transition-colors hover:text-foreground md:h-8 md:w-8"
          >
            <LineChart class="h-5 w-5" />
            <span class="sr-only">Analytics</span>
          </a>
        </TooltipTrigger>
        <TooltipContent side="top">
          Analytics
        </TooltipContent>
      </Tooltip>
    </TooltipProvider>
  </nav>

</aside>

</template>

<script setup lang="ts">
import {
  MessageCircleCode,
  BookOpenText,
 
  Home,
  LineChart,


  Package2,

  Search,
  Settings,

  Users2,
} from 'lucide-vue-next'

</script>