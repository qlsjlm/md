<script setup lang="ts">
const aboutDialogVisible = ref(false)
</script>

<template>
  <MenubarMenu>
    <MenubarTrigger>
      Ai
    </MenubarTrigger>
    <MenubarContent align="start">
      <MenubarCheckboxItem @click="aboutDialogVisible = true">
        <span>使用Ai</span>
      </MenubarCheckboxItem>
    </MenubarContent>
  </MenubarMenu>

  <AboutDialog :visible="aboutDialogVisible" @close="aboutDialogVisible = false" />
</template>
