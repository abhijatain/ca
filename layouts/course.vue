<template>
     <SideBar />
     <BottomBar />
    <div class=" md:ms-14 ">
        <div class="flex  justify-between p-4">
            <div class="text-2xl font-bold">
                
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
            <CourseNav />
            <div class="mt-auto">
              <Card>
                <CardHeader>
                  <CardTitle>Upgrade to Pro</CardTitle>
                  <CardDescription>
                    Unlock all features and get unlimited access to our
                    support team.
                  </CardDescription>
                </CardHeader>
                <CardContent>
                  <Button size="sm" class="w-full">
                    Upgrade
                  </Button>
                </CardContent>
              </Card>
            </div>
          </ScrollArea>
          </SheetContent>
                </Sheet>
                AFM
            </div>
            <div>
                <Timer />
            </div>
        </div>     
    </div>
    <Separator class="h-1"/>
    <div class="md:ms-14 flex flex-row mb-14">
        <div class="w-[15%]  p-2 h-screen hidden md:block">
            <CourseNav />
        </div>
        <div class="w-[100%] flex flex-col gap-6 border-l">
            <slot />
        </div>
    </div>
</template>

<script setup lang="ts">
import {  Menu } from 'lucide-vue-next'
</script>