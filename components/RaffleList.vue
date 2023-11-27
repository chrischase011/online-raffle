<script lang="ts" setup>

const emit = defineEmits(['getList'])
const data = defineProps(['picked'])

const list = ref("")


watch(() => data.picked, (newPicked) => {
  // Remove the picked value from the list
  const _list = list.value.split("\n")
  const index = _list.indexOf(newPicked);
  if (index !== -1) {
    _list.splice(index, 1);
  }
  list.value = _list.join("\n");
  emit('getList', list.value)
});


const handleChange = () => {
  emit('getList', list.value)
}
</script>

<template>
  <div>
    <label class="fw-bold">Input the names here (1 item per line)</label><br>
    <textarea id="list" class="form-control" rows="12" v-model="list" @change="handleChange"
      style="background-color: transparent;"></textarea>
  </div>
</template>

<style scoped></style>
