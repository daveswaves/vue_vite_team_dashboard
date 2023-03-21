<script setup>
import TeamHeader from '@/components/teams/TeamHeader.vue';
import TeamMain from '@/components/teams/TeamMain.vue';
import TeamFooter from '@/components/teams/TeamFooter.vue';
import { useTeamStore } from '@/stores/TeamStore';

let team = useTeamStore();
team.fill();

setTimeout(() => {
   team.spots = 10;
}, 3000);

setTimeout(() => {
   team.grow(20);
}, 6000);
</script>

<template>
   <TeamHeader />

   <div class="place-self-center flex flex-col gap-y-3">
      <TeamMain />
   </div>

   <TeamFooter />
</template>