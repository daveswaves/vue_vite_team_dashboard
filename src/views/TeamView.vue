<script setup>
import TeamHeader from '@/components/teams/TeamHeader.vue';
import TeamMain from '@/components/teams/TeamMain.vue';
import TeamFooter from '@/components/teams/TeamFooter.vue';
import team from '@/team.json';
</script>

<template>
   <TeamHeader :team="team" />

   <div class="place-self-center flex flex-col gap-y-3">
      <TeamMain :team="team" />
   </div>

   <TeamFooter :team="team" />
</template>