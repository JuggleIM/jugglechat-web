<script setup>
import { reactive } from "vue";
import utils from "../common/utils";
const props = defineProps(['message']);
let { content: { type },isSender, sender, conversationTitle } = props.message;
let opName = type == 0 ? '添加' : '通过';
let tip = `${sender.name} ${opName} 你 为好友`;
if(isSender){
  tip = `你 ${opName} ${conversationTitle} 为好友`;
}
let state = reactive({
  label: tip
});
</script>

<template>
  <div class="tyn-reply-separator">
    <span class="tyn-separator-item">
      {{ state.label }}
    </span>
  </div>
</template>
