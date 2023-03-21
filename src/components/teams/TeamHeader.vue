<script setup>
import { useTeamStore } from '@/stores/TeamStore';
import AddMemberModal from '@/components/teams/AddMemberModal.vue';
let team = useTeamStore();
</script>

<template>
   <header class="flex justify-between">
      <div>
         <AddMemberModal />
      </div>

      <div>
         <h3>{{ team.name }} Team</h3>
      </div>
   </header>
</template>