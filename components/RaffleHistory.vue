<script lang="ts" setup>

const data = defineProps(['picked'])

const history = ref("")

watch(() => data.picked, (newPicked) => {
  history.value += (newPicked + '\n')
});


function resetHistory() {
  history.value = ""
}

</script>

<template>
  <div>
    <label>History</label><br>
    <textarea id="list" class="form-control" rows="10" v-model="history" style="background-color: transparent;"
      readonly></textarea>
    <button type="button" class="my-3 btn btn-sm btn-primary float-end" @click="resetHistory">Reset</button>
  </div>
</template>

<style scoped></style>
