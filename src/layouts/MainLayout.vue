<template>
  <q-layout 
    view="lHh Lpr lFf"
    :class="['custom-layout no-shadow']"
    >
    <div class="bg-gradient">
      <CstmHeader />
      <CstmBody />
    </div>
    <CstmBottom />
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import CstmHeader from 'components/Header.vue'
import CstmBody from 'components/Body.vue'
import CstmBottom from 'components/Bottom.vue'

defineOptions({
  name: 'MainLayout'
})

</script>

