<script setup lang="ts">
const props = defineProps({
  visible: {
    type: Boolean,
    default: false,
  },
})

const emit = defineEmits([`close`])

function onUpdate(val: boolean) {
  if (!val) {
    emit(`close`)
  }
}

const links = [
  { label: `ChatGPT国内版`, url: `https://chat.tvvai.com` },
  { label: `Ai工具站`, url: `https://ai.tvvai.com` },
  { label: `Ai学习联盟`, url: `https://sd.tvvai.com` },
]

function onRedirect(url: string) {
  window.open(url, `_blank`)
}
</script>

<template>
  <Dialog :open="props.visible" @update:open="onUpdate">
    <DialogContent>
      <DialogHeader>
        <DialogTitle>Ai</DialogTitle>
      </DialogHeader>
      <div class="text-center">
        <h3>一款高度简洁的微信 Markdown 编辑器</h3>
        <p>扫码关注公众号 青年设计联盟，让Ai应用于工作，成为生产力！</p>
        <img
          class="mx-auto my-5"
          src="https://img.tvvai.com/qnsjlm.jpg"
          alt="青年设计联盟"
          style="width: 40%"
        >
      </div>
      <DialogFooter class="sm:justify-evenly">
        <Button
          v-for="link in links"
          :key="link.url"
          @click="onRedirect(link.url)"
        >
          {{ link.label }}
        </Button>
      </DialogFooter>
    </DialogContent>
  </Dialog>
</template>
