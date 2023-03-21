<script setup>
import Modal from '@/components/Modal.vue';
import { ref } from 'vue';

import { useTeamStore } from '@/stores/TeamStore';

let showModal = ref(false);
let team = useTeamStore();
</script>

<template>
   <button class="
      bg-green-500
      hover:bg-green-400
      text-white
      px-4 py-2
      rounded
      disabled:bg-gray-400"
      :disabled="!team.spotsRemaining"
      @click="showModal=true"
   >Add Member ({{ team.spotsRemaining }} spots left)</button>
   
   <!-- Teleport stops Modal being nested in existing tags and positions it next to the closing body tag -->
   <Teleport to="body">
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
   </Teleport>
</template>