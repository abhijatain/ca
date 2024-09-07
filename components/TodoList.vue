<script setup lang="ts">
import {
  Table,
  TableBody,
  TableCaption,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from '@/components/ui/table'

const tasks = ref([
  {
    "task_name": "Complete project report",
    "due_date": "2024-09-06",
    "priority": "high",
    "complete": false,
    "tags": ["work", "urgent"]
  },
  {
    "task_name": "Review team meeting notes",
    "due_date": "2024-09-07",
    "priority": "medium",
    "complete": true,
    "tags": ["work", "review"]
  },
  {
    "task_name": "Fix website bug",
    "due_date": "2024-09-08",
    "priority": "high",
    "complete": false,
    "tags": ["development", "critical"]
  },
  {
    "task_name": "Prepare presentation slides",
    "due_date": "2024-09-10",
    "priority": "low",
    "complete": false,
    "tags": ["presentation", "low-priority"]
  },
  {
    "task_name": "Send email to client",
    "due_date": "2024-09-09",
    "priority": "medium",
    "complete": true,
    "tags": ["communication", "client"]
  },
 
])

</script>

<template>
    <div class="flex justify-between align-center p-2">
        <h1 class="font-bold text-2xl">Todo List</h1>
        <Button>Manage Tasks</Button>
    </div>
    <Table>
      
      <TableHeader>
        <TableRow>
          <TableHead class="w-[100px]">Status</TableHead>
          <TableHead>Title</TableHead>
          <TableHead>Priority</TableHead>
          <TableHead>Due Date</TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        <TableRow v-for="task in tasks" :key="task.task_name">
          <TableCell class="font-medium">
            <div class="flex items-center space-x-2">
              <Checkbox v-model="task.complete" :checked="task.complete" @click="task.complete=!task.complete" />
            </div>
          </TableCell>
          <TableCell>{{ task.task_name }}</TableCell>
          <TableCell>{{ task.priority }}</TableCell>
          <TableCell>{{ task.due_date }}</TableCell>
        </TableRow>
      </TableBody>
    </Table>
  </template>