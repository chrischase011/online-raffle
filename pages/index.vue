<script lang="ts" setup>

const lists = ref("")
const picked = ref("")

const getLists = (list) => {
  lists.value = list
}

const getPicked = (value) => {
  picked.value = value
}

</script>

<template>
  <div class="container my-3">
    <div class="row">
      <div class="col-12 col-md-9 border-end">
        <Raffle :lists="lists" @picked="getPicked" />
      </div>
      <div class="col-12 col-md-3 border-start">
        <div class="row">
          <div class="col-12">
            <RaffleList @getList="getLists" :picked="picked" />
          </div>
          <div class="my-3 col-12">
            <RaffleHistory :picked="picked" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
