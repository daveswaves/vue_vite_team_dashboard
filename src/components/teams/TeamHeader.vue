<script setup>
import { useTeamStore } from '@/stores/TeamStore';
let team = useTeamStore();
</script>

<template>
   <header class="flex justify-between">
      <div>
         <button class="
         bg-green-500
         hover:bg-green-400
         text-white
         px-4 py-2
         rounded
         disabled:bg-gray-400"
         :disabled="!team.spotsRemaining">Add Member ({{ team.spotsRemaining }} spots left)</button>
      </div>

      <div>
         <h3>{{ team.name }} Team</h3>
      </div>
   </header>
</template>