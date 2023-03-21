<script setup>
defineProps({
   show: Boolean
})
</script>

<template>
   <Transition name="modal">
   <!--
   <Transition
      enter-from-class="opacity-0 scale-125"
      enter-to-class="opacity-100 scale-100"
      enter-active-class="transition duration-300"

      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
      leave-active-class="transition duration-200"
   >
   -->
      <div v-if="show" class="modal-mask">
         <div class="modal-container">
            <!-- <header>
               <slot name="header">default header</slot>
            </header> -->

            <div>
               <slot>default body</slot>
            </div>

            <footer class="modal-footer">
               <button @click="$emit('close')">Close</button>
            </footer>
         </div>
      </div>
   </Transition>
</template>

<style scoped>
.modal-mask {
   position:fixed;
   inset: 0;
   background: rgba(0, 0, 0, .6);
   display: grid;
   place-items: center;
}

.modal-container {
   background: white;
   color: black;
   padding: 1rem;
   width: 80vw;
   max-width: 600px;
   border-radius: 7px;
}

.modal-footer {
   border-top: 1px solid #ddd;
   margin-top: 1rem;
   padding-top: .5rem;
   font-size: .8rem;
}

.modal-footer button {
   background: #ddd;
   padding: .25rem .75rem;
   border-radius: 20px;
}
.modal-footer button:hover {
   background: #ccc;
}

.modal-enter-from {
   opacity: 0;
   scale: 125%;
}
.modal-enter-to {
   opacity: 100;
   scale: 100%;
}
.modal-enter-active {
   transition: opacity .5s, scale .5s;
}
</style>