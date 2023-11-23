<script lang="ts" setup>

const data = defineProps(['lists'])
const emit = defineEmits(['picked'])

const { $anime } = useNuxtApp()

const text = ref("")
const picked = ref("")

const handleShakeAndDraw = () => {
  if (data.lists === null || data.lists === undefined || data.lists === "") {

    alert("Please provide list of names")
    return
  }
  const lists = data.lists.split("\n")

  $anime({
    targets: ".box",
    translateY: [
      { value: '-7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '-7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '0', duration: 100, easing: 'easeInOutQuad' },
    ],
    translateX: [
      { value: '-7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '-7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '7px', duration: 100, easing: 'easeInOutQuad' },
      { value: '0', duration: 100, easing: 'easeInOutQuad' },
    ],
    loop: 4
  })

  setTimeout(() => {

    const shuffList = shuffleList(lists)
    picked.value = shuffList[0]
    isAWinnerPicked(shuffList[0])

    $("#mdlWinner").modal('show')
    console.log(shuffList)
  }, 2000);

  // text.value = data.lists
}

const isAWinnerPicked = (value) => {
  emit('picked', value)
}

// using the Fisher-Yates shuffling
function shuffleList<T>(array: T[]): T[] {
  const arr = [...array];

  for (let i = arr.length - 1; i > 0; i--) {
    let x = Math.floor(Math.random() * (i + 1));

    if (x !== null && x !== undefined) {
      [arr[i], arr[x]] = [arr[x], arr[i]];
    }
  }

  return arr;
}

</script>

<template>
  <div class="w-100 d-flex justify-content-center flex-column align-items-center mb-5">
    <img src="/img/box2.png" class="box">
    <p>{{ text }}</p>
    <button type="button" class="btn btn-primary" @click="handleShakeAndDraw">Shake & Draw</button>
  </div>


  <div class="modal fade" id="mdlWinner" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1">
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">Congratulations</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <h3>{{ picked }}</h3>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.box {
  width: 100%;
  max-width: 450px;
  height: 450px;
}
</style>
