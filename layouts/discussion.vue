<template>

  <div class="lg:ms-14">
    <!-- Sidebar Component -->
    <SideBar />
    

    <!-- Header Section -->
    <div class="flex justify-between p-4">
        
      <div class="text-2xl font-bold text-center">
     
        Community
      </div>
      <Sheet>
          <SheetTrigger as-child>
            <Button
              variant="outline"
              size="icon"
              class="shrink-0 md:hidden"
            >
              <Menu class="h-5 w-5" />
              <span class="sr-only">Toggle navigation menu</span>
            </Button>
          </SheetTrigger>
          <SheetContent side="left" class="flex flex-col">
            <ScrollArea>
            <DiscussionNav />
        </ScrollArea>
           
          </SheetContent>
                </Sheet>
    </div>

    <!-- Separator -->
    <Separator class="h-1 bg-primary"/>

    <!-- Header Slot (Named Slot) -->
    <header>
      <slot name="header"></slot>
    </header>

    <!-- Main Content -->
    <main>
      <div class="flex gap-2 md:p-4 flex-col md:flex-row ">
        
        <!-- CourseNav Section (Left Column) -->
        <div class="w-[25%] border-r hidden md:block">
          <DiscussionNav />
        </div>

        <!-- Slot Content (Middle Column) -->
        <div class="flex flex-col gap-2 md:w-[75%] lg:w-[55%] md:p-0 p-2 ">
          <slot />
        </div>

        <!-- Right Column -->
        <div class="lg:w-[30%] flex flex-col gap-4 border-l hidden lg:block">
          
          <!-- Top Threads Card -->
          <Card class="border-0 rounded-none shadow-none">
            <CardHeader class="text-center">
              <CardTitle>Top Threads</CardTitle>
              <CardDescription>Read our most read threads to get insight on these topics.</CardDescription>
            </CardHeader>
            <CardContent>
              <DiscussionCard3 />
              <DiscussionCard3 />
              <DiscussionCard3 />
              <DiscussionCard3 />
            </CardContent>
          </Card>
          
          <!-- Recommended Threads Card -->
          <Card class="border-0 rounded-none shadow-none">
            <CardHeader class="text-center">
              <CardTitle>Recommended Threads</CardTitle>
              <CardDescription>Read our most read threads to get insight on these topics.</CardDescription>
            </CardHeader>
            <CardContent>
              <DiscussionCard3 />
              <DiscussionCard3 />
              <DiscussionCard3 />
              <DiscussionCard3 />
            </CardContent>
          </Card>

        </div>
      </div>
    </main>

    <div class="mt-6"></div>
  </div>
</template>

<script setup lang="ts">
import {  Menu } from 'lucide-vue-next'
</script>