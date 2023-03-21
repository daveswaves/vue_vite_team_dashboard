<script setup>
import TeamHeader from '@/components/teams/TeamHeader.vue';
import TeamMain from '@/components/teams/TeamMain.vue';
import TeamFooter from '@/components/teams/TeamFooter.vue';
import Modal from '@/components/Modal.vue';
import { useTeamStore } from '@/stores/TeamStore';
import { ref } from 'vue';

let team = useTeamStore();
team.fill();

let showModal = ref(false);

/* 
setTimeout(() => {
   team.spots = 10;
}, 3000);

setTimeout(() => {
   team.grow(20);
}, 6000);
 */
</script>

<template>
   <TeamHeader @add="showModal=true" />

   <div class="place-self-center flex flex-col gap-y-3">
      <TeamMain />
   </div>

   <TeamFooter />

   <Modal :show="showModal" @close="showModal=false">
      <!-- <template #header>header override</template> -->
      <template #default>
         <p>Need to add a new member to team?</p>

         <form class="mt-6">
            <div class="flex gap-2">
               <input type="email" placeholder="Enter Email" class="flex-1">
               <button>Add</button>
            </div>
         </form>
      </template>
   </Modal>
</template>