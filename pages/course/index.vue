<template>
    
            <div class="flex gap-4 border-b flex-col md:flex-row">
                <Pomodoro class="md:w-[50%] lg:w-[30%]"/>
                <div class="flex flex-col md:w-[50%] lg:w-[70%] p-2">
                    <TodoList />
                </div>
               
            <PieChart class=" my-auto hidden"/>
            
            </div>
            <div class="flex gap-4 flex-col md:flex-row">
                <div class="md:w-[60%] p-2">
                <div class="flex justify-between align-center p-2">
                    <h1 class="text-2xl font-bold mb-3">Latest Discussions</h1>
                     <Button>View All</Button>
                </div>
                <div class="flex flex-col gap-2">
                    <DiscussionCard3 />
                 
                    <DiscussionCard3 />
                    <DiscussionCard3 />
                    
                </div>
            </div>
            <Card class="p-2 border-0 border-b rounded-none shadow-none">
                <CardHeader>
                    <CardTitle>Roadmap</CardTitle>
                    <CardDescription>We have a bank of 50 questions for this chapter with doubt clearing support in community.Attempt them on our portal with progress tracking</CardDescription>
                </CardHeader>
                <CardContent class="flex gap-4 flex-col md:flex-row">
                    <img src="assets/example1.png" class="rounded-lg w-[200px]"/>
                    <img src="assets/example2.png"  class="rounded-lg w-[200px]"/>
                </CardContent>
                <CardFooter>
                    <Button variant="link">Practice</Button>
                </CardFooter>
            </Card>
            </div>
            
      
  

</template>


<script setup lang="ts">
definePageMeta({
  layout: 'course'
})

import { Bell, CircleUser, Home, LineChart, Menu, Package, Package2, Search, ShoppingCart, Users } from 'lucide-vue-next'
const goals = ref([
    {'name':"Advanced role of CFO in various matters including value"},
    {'name':"Strategic Financial Decision Making Framework"},
    {'name':"Strategy at Different Hierarchy Levels"},
    {'name':"Financial Planning"},
    {'name':"Interface of Financial Policy and Strategic Management"},
    {'name':"Balancing Financial Goals vis-à-vis Sustainable Growth"},
])

</script>