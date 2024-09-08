<script setup lang="ts">
import DarkMode from '~/components/DarkMode.vue';
</script>

<template>
    <SideBar />
    <div class="md:ms-14 p-4  flex gap-2 flex-col ">
        <div class="flex flex-col md:flex-row justify-between items-center">
            <h1 class="font-bold text-4xl my-3">The Student Hub</h1>
           
            <Timer />
        </div>
        
        <p class="text-slate-500">If you are working on something that you really care about, you don't have to be pushed.</p>
        <Separator class="h-2 bg-primary"/>
        <div class="flex mt-2 gap-8 justify-between flex-col md:flex-row">
            <Pomodoro class="md:w-[30%]"/>
            <div class="md:w-[60%]">
                <div class="flex justify-between align-center p-2">
                    <h1 class="text-2xl font-bold mb-3">Study Material</h1>
                     <Button>View All</Button>
                </div>
                
                <div class="flex gap-6 flex-col md:flex-row ">
                    <Card class="md:w-[300px]">
                    <CardHeader class="bg-primary text-white">
                        <CardTitle>
                            Foundation
                        </CardTitle>
                        <CardDescription class="text-white">
                            Currently We Have two subjects of foundation level
                        </CardDescription>
                    </CardHeader>
                    <CardContent>
                        <div class="flex flex-col ">
                            <Button variant="link" class="p-0 justify-start text-black dark:text-white">Syllabus</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Discussions</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Previous Year Questions</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Chapter Wise Questions</Button>
                           
                       </div>
                    </CardContent>
                </Card>
                <Card class="md:w-[300px]">
                    <CardHeader class="bg-primary text-white">
                        <CardTitle>
                            Inter
                        </CardTitle>
                        <CardDescription class="text-white">
                            Currently We Have two subjects of Inter level
                        </CardDescription>
                    </CardHeader>
                    <CardContent>
                        <div class="flex flex-col ">
                            <Button variant="link" class="p-0 justify-start text-black dark:text-white">Syllabus</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Discussions</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Previous Year Questions</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Chapter Wise Questions</Button>
                           
                       </div>
                    </CardContent>
                </Card>
                <Card class="md:w-[300px]">
                    <CardHeader class="bg-primary text-white">
                        <CardTitle>
                            Finals
                        </CardTitle>
                        <CardDescription class="text-white">
                            Currently We Have two subjects of final level
                        </CardDescription>
                    </CardHeader>
                    <CardContent>
                        <div class="flex flex-col ">
                            <Button variant="link" class="p-0 justify-start text-black dark:text-white">Syllabus</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Discussions</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Previous Year Questions</Button>
                           <Button variant="link" class="p-0 justify-start text-black dark:text-white">Chapter Wise Questions</Button>
                           
                       </div>
                    </CardContent>
                </Card>
         
                </div>
            </div>
            
            <div class="md:w-[30%]  ">
                <Card class="p-4">
                    <DailyChart />
                </Card>
              
            </div>
        
           
        </div>
        <div class="mt-4">
         
            <div class="flex mt-3 gap-6 flex-col md:flex-row">
                <div class="md:w-[50%]">
                    <Card class="p-4">
                        <TodoList />
                    </Card>
                    
            </div>
            <div class="md:w-[50%]">
                <Card class="p-4">
                    <LatestUpdates />
                </Card>
               
                
            </div>
                
            </div>
        </div>
        <div class="mt-4 flex gap-6 flex-col md:flex-row">
            <div class="md:w-[70%]">
                <Card class="p-4">
                <div class="flex justify-between align-center p-2">
                    <h1 class="text-2xl font-bold mb-3">Latest Discussions</h1>
                     <Button>View All</Button>
                </div>
                <div class="flex flex-col gap-2">
                    
                    <DiscussionCard />
                 
                    <DiscussionCard />
                    <DiscussionCard />
                    <DiscussionCard />
                    <DiscussionCard />
                </div>
            </Card>
            </div>
            
            <div class="md:w-[40%]">
                
                <div class="flex flex-col gap-2">
                    <Card class=" md:border-l ">
                    <CardHeader class="text-center">
                        <CardTitle>Your Contributions</CardTitle>
                        <CardDescription>Read our most read threads to get insight on these topics.</CardDescription>
                        
                    </CardHeader>
                    <CardContent>
                        <DiscussionCard3 />
                <DiscussionCard3 />
                <DiscussionCard3 />
                <DiscussionCard3/>
                    </CardContent>
                </Card>
                
                </div>
            </div>
            
                
        </div>
        <div class="mt-6">

        </div>
    </div>
</template>

