<template>
    <div class="flex justify-between align-center p-2">
        <h1 class="font-bold text-2xl">Latest Updates</h1>
        <Button>View All</Button>
    </div>
    <Table>
      
      <TableHeader>
        <TableRow>
          
          <TableHead>Date</TableHead>
          <TableHead>Title</TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        <TableRow v-for="update in updates" :key="update.title">
         
          
          <TableCell>{{ update.date }}</TableCell>
          <TableCell>{{ update.title }}</TableCell>
        </TableRow>
      </TableBody>
    </Table>
</template>

<script setup>
const updates = [
{
    "title": "New Feature Released: Dark Mode",
    "date": "2024-09-01"
  },
  {
    "title": "Bug Fix: Resolved Login Issue",
    "date": "2024-09-02"
  },
  {
    "title": "Performance Improvement: Faster Loading Time",
    "date": "2024-09-03"
  },
  {
    "title": "UI Update: Enhanced Dashboard Design",
    "date": "2024-09-04"
  },
  {
    "title": "Security Update: Password Strength Enhancements",
    "date": "2024-09-05"
  }
]

</script>