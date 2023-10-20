<script setup lang="ts">
import { Icon } from '@iconify/vue'
</script>

<template>
  <div class="kun-toolbar">
    <!-- kunditor button -->
    <div class="btn">
      <!-- font size -->
      <div class="kun-group">
        <span><Icon icon="material-symbols:format-h1-rounded" /></span>
        <span><Icon icon="material-symbols:format-h2-rounded" /></span>
      </div>

      <!-- font style -->
      <div class="kun-group">
        <span><Icon icon="material-symbols:format-bold-rounded" /></span>
        <span>
          <Icon icon="material-symbols:strikethrough-s-rounded" />
        </span>
        <span><Icon icon="material-symbols:format-italic-rounded" /></span>
      </div>

      <!-- list style -->
      <div class="kun-group">
        <span>
          <Icon icon="material-symbols:format-list-bulleted-rounded" />
        </span>
      </div>

      <!-- text position -->
      <div class="kun-group">
        <span>
          <Icon icon="material-symbols:format-align-center-rounded" />
        </span>
      </div>

      <!-- text color -->
      <div class="kun-group">
        <span>
          <Icon icon="material-symbols:format-color-text-rounded" />
        </span>
      </div>

      <!-- quote, code -->
      <div class="kun-group">
        <span>
          <Icon icon="material-symbols:format-quote-rounded" />
        </span>
        <span>
          <Icon icon="material-symbols:code-blocks-outline-rounded" />
        </span>
      </div>
    </div>

    <!-- some kunditor functions -->
    <div class="func"></div>
  </div>
</template>

<style lang="scss" scoped>
.kun-toolbar {
  background-color: var(--kungalgame-trans-blue-0);
  border-bottom: 1px solid var(--kungalgame-blue-4);
  width: 100%;
}

.btn {
  display: flex;
  flex-wrap: wrap;
  padding: 5px;

  .kun-group {
    display: flex;

    span {
      margin-left: 5px;
      padding: 2px 7px;
    }
  }
}
</style>
