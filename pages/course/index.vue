<template>
    
            <div class="flex gap-4 border-b flex-col md:flex-row">
                <Pomodoro class="md:w-[30%]"/>
                <div class="flex flex-col md:w-[70%] p-2">
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
               
            <Card class="p-2 border-0 rounded-none shadow-none">
                <CardHeader>
                    <CardTitle>Notes</CardTitle>
                    <CardDescription>Notes are an integral part of self study. If you have notes store them with us for safe keeping and managing them. If not take notes on our portal and there are two ways you can do that:</CardDescription>
                </CardHeader>
                <CardContent class="flex gap-4">
                    <Tabs default-value="account" >
                        <TabsList class="grid w-full grid-cols-2">
                        <TabsTrigger value="account">
                            ICAI PDF
                        </TabsTrigger>
                        <TabsTrigger value="password">
                            Self Notes
                        </TabsTrigger>
                        </TabsList>
                        <TabsContent value="account">
                        <Card>
                            <CardHeader>
                                <CardTitle>ICAI</CardTitle>
                           
                            <CardDescription>
                               Use PDF provided by ICAI to take notes on, by highlighting or adding comments on it.
                            </CardDescription>
                            </CardHeader>
                            <CardContent class="space-y-2">

                            </CardContent>
                            <CardFooter>
                            <Button>Take Notes</Button>
                            </CardFooter>
                        </Card>
                        </TabsContent>
                        <TabsContent value="password">
                        <Card>
                            <CardHeader>
                            <CardTitle>Password</CardTitle>
                            <CardDescription>
                                Change your password here. After saving, you'll be logged out.
                            </CardDescription>
                            </CardHeader>
                            <CardContent class="space-y-2">
                            <div class="space-y-1">
                                <Label for="current">Current password</Label>
                                <Input id="current" type="password" />
                            </div>
                            <div class="space-y-1">
                                <Label for="new">New password</Label>
                                <Input id="new" type="password" />
                            </div>
                            </CardContent>
                            <CardFooter>
                            <Button>Save password</Button>
                            </CardFooter>
                        </Card>
                        </TabsContent>
                    </Tabs>
                </CardContent>
            
            </Card>
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