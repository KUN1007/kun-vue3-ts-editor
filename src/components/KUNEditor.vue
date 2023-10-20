<script setup lang="ts">
import { onMounted, ref } from 'vue'

// kunditor ref
const kunditor = ref<HTMLElement | null>(null)
// placeholder
const kunPlaceholder = ref('Input text here...')
// kunditor blur class
const kunBlurClass = ref('')

// on start editing
const startEditing = () => {
  if (kunditor.value) {
    kunditor.value.contentEditable = 'true'
    kunditor.value.focus()
  }
}

// on kunditor focus
const handleKunditorFocus = () => {
  kunPlaceholder.value = ''
  kunBlurClass.value = ''
}

// on kunditor blur
const handleKunditorBlur = () => {
  console.log(getPlainText())

  if (kunditor.value && !getPlainText().trim()) {
    kunPlaceholder.value = 'Input text here...'
  }
  kunBlurClass.value = 'blur'
}

onMounted(() => {
  if (kunditor.value) {
    kunditor.value.contentEditable = 'true'
    kunditor.value.focus()
  }
})

// get kunditor rich text
const getRichText = () => {
  if (kunditor.value) {
    return kunditor.value.innerHTML
  }
  return ''
}

// get kunditor plain text
const getPlainText = () => {
  if (kunditor.value) {
    return kunditor.value.innerText
  }
  return ''
}
</script>

<template>
  <div class="kun-container">
    <div
      tabindex="0"
      ref="kunditor"
      class="kunditor"
      :class="[kunBlurClass]"
      @click="startEditing"
      @focus="handleKunditorFocus"
      @blur="handleKunditorBlur"
    >
      <p class="kun-placeholder">{{ kunPlaceholder }}</p>
    </div>
  </div>
</template>

<style lang="scss">
.kun-container {
  height: 777px;
  width: 90%;
  margin: 0 auto;
  margin-top: 20px;
  background-color: var(--kungalgame-trans-blue-0);
  border: 1px solid var(--kungalgame-blue-4);
  color: var(--kungalgame-font-color-3);
}

.kunditor {
  height: 100%;
  position: relative;
  padding: 7px;
}

.kun-placeholder {
  font-style: oblique;
}

.blur {
  color: var(--kungalgame-font-color-1);
}
</style>
